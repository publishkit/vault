---
title: Plugins
alias: Plugins, $plugins
description: Plugins
---
# Plugins

Everything on the page that is not the "actual content" is defacto rendered by a plugin.

Plugins are the core design principle of PublishKit. Without any plugins, content is rendered as is, without any transformations, onto the page. But with plugins, that's where the magic begins. Plugins can do anything. From fully tweaking and theming the UI, to creating and binding ui elements, or just exposing functions for other plugins to consume. The `kit` comes equiped with some `core` plugins out of the box. Other plugins are imagined and delivered by the `community`.

Everything in the `kit`  is a plugin. Combined, plugins can delivers powerful characteristics, like turning independant static pages into fully featured web apps.

- list of [[plugins/core/index|Core Plugins]]
- list of [[plugins/community/index|Community Plugins]]
- [[create|Create a plugin]]

## usage

Plugins can be added and overided, taking precedence, in the frontmatter of the following files:
- the `kitrc.md` - [[doc/services/kitrc|$kitrc]]
- any `dirrc.md` file in any directory
- individual files
- in url - see [[url injection]]

To register a plugin, in the frontmatter of any of the files mentionned above, add a key value pair under the `plugins` yaml object. Use the plugin name for the key, and set a `true` value. Ex:

```yaml
plugins:
  header: true
  navbar: true
  darkmode: true
```

Note that only `core` and `local` plugins can register by simply specifying a `true` value. That's because their are included in the kit (for core plugins) or auto resolve (for local plugins). 

`community` plugins can just prefix the plugin name with a `@` sign, and `external` plugins have to specify their location with an url.

So depending on where the plugin live, you will register it differently. Exemple with the `ga`  plugin:

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

You can of course, in any page, overide the `kitrc` config or disable the plugin like so:

```yaml
plugins:
  ga: false
```

## options

Plugins can have options. For exemple the `ga` community plugin takes a google tracking `id`. At the root of the frontmatter, create a yaml object with the plugin name, and provide the option in a key value manner:

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

Plugins are orchestred in the following way:

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

In fact those are the 8 lines of code that compose the `kit` main function. Pugins can implement any of the following methods of the lifecycle:
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
