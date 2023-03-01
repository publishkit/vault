---
title: Plugins
alias: Plugins, $plugins
description: Plugins
---
# Plugins

Everything on the page that is not the "actual content" is rendered by a plugin.

Plugins are the core design principle of the Kit. Without any plugins, content is rendered as is, without any transformations, onto the page. But with plugins, that's where the magic begins. Plugins can do anything. From fully tweaking and theming the UI, to creating and binding UI elements, or just exposing functions for other plugins to consume. The `kit` comes equipped with some `core` plugins out of the box. Other plugins are imagined and delivered by the `community`.

Everything in the `kit`  is a plugin. Combined, plugins can deliver powerful characteristics, like turning independent static pages into fully featured web apps.

- list of [[plugins/core/index|Core Plugins]]
- list of [[plugins/community/index|Community Plugins]]
- [[create|Create a plugin]]

## usage

Plugins can be added and overrided, taking precedence, in the frontmatter of the following files:
- the `kitrc.md` - [[doc/services/kitrc|$kitrc]]
- any `dirrc.md` file in any directory
- individual files
- in url - see [[url injection]]

To register a plugin, in the frontmatter of the files mentioned above, add a key value pair under the `plugins` YAML object. Use the plugin name for the key, and set a `true` value. Ex:

```yaml
plugins:
  header: true
  navbar: true
  darkmode: true
```

Note that only `core` and `local` plugins can register by simply specifying a `true` value. That's because they are included in the kit (for core plugins) or auto resolve (for local plugins). 

`community` plugins can just prefix the plugin name with a `@` sign, and `external` plugins have to specify their location with a URL.

So, depending on where the plugin lives, you will register it differently. Example with the `ga`  plugin:

```yaml
plugins:
  # local
  ga: true
  # community
  ga: "@ga"
  # external
  ga: "https://url.com/ga.js"
```

### local plugins

They have to be located in the `kit_local/plugins` folder at the root of your `kit`. Ex: 

```text
📂 kit_folder
 ┃ 
 ┣ 📂 kit_local
 ┃ ┗ 📂 plugins
 ┃   ┗ 📄 ga.js
 ┃   ┗ 📄 my-new-plugin.js
 ┃ 
 ┣ 📄 index.html
 ┣ 📄 kitrc.json
 ┣ ...
```

### community plugins

It turns out the [[ga|ga]] plugin is an actual community plugin, that you can use right now. I would suggest adding this particular plugin in your `kitrc` config, so all your pages can benefit from the tracking. 

```yaml
plugins:
  ga: "@ga"
```

You can of course, in any page, override the `kitrc` config or disable the plugin like so:

```yaml
plugins:
  ga: false
```

## options

Plugins can have options. For example, the `ga` community plugin takes a Google tracking `id`. At the root of the frontmatter, create a YAML object with the plugin name, and provide the option in a key value manner:

```yaml
# register plugins
plugins:
  header: true
  navbar: true
  darkmode: true
  ga: "@ga"

# plugins options
header:
  fluid: true

ga:
  id: "G-MDGQ40965Q"
```

For single option plugins, [[short syntax]] can be used:

```yaml
plugins:
  header: "fluid:true"
  navbar: true
  darkmode: true
  ga: "@ga|id:G-MDGQ40965Q"
```


## life cycle

Plugins are orchestrated in the following way:

```js
await plugins.init();
await plugins.deps();
await plugins.render();
await plugins.style();
await ui.render();
await plugins.transform();
await ui.draw();
await plugins.bind();
```

In fact, those are the 8 lines of code that compose the `kit` main function. Plugins can implement any of the following methods of the lifecycle:
- `init`
- `deps`
- `render`
- `style`
- `transform`
- `bind`

## api

> [!note] 
> - Each plugin is exposed globally by it's name prefixed by a `$`. 
> - Interacting with a plugin is as simple as `$navbar.toggle()` or `$stripe.pay()`.
> 