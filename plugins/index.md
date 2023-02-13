---
title: Plugins
alias: Plugins, $plugins
description: Plugins
---
# Plugins

Everything on the page that is not the "actual content" is defacto rendered by a plugin.

Plugins are the core design principle of PublishKit. Without any plugins, content is rendered as is, without any transformations, onto the page. But with plugins, that's where the magic begins. Plugins can do anything. From fully tweaking and theming the UI, to creating and binding ui elements, or just exposing functions for other plugins to consume. The `kit` comes equiped with some `core` plugins out of the box. Other plugins are imagined and delivered by the `community`.

Everything in the `kit`  framework is a plugin. Combined, plugins can delivers powerful characteristics, like turning independant static pages into fully featured web apps.

- list of [[plugins/core/index|Core Plugins]]
- list of [[plugins/community/index|Community Plugins]]

> [!note] 
> We encourage cross plugin communication, by providing elegant and higher level api's. Each plugin is exposed globaly in the page, using it's name prefixed by a `$`. Interacting with a plugin is as easy as `$navbar.toggle()` or `$stripe.pay()`.
> 

## usage

Plugins can be added and overided, taking precedence, in the frontmatter of the following files:
- the `kitrc.md` file at the root of your vault (global config)
- any `dirrc.md` file in any directory
- individual content files
- in url - see [[url injection]]

To register a plugin, in the frontmatter of any of the files mentionned above, add a key value pair under the `plugins` yaml object. Use the plugin name for the key, and set a `true` value. Ex:

```yaml
plugins:
  header: true
  navbar: true
  darkmode: true
```

Note that only `core` and `local` plugins can register by simply specifying a `true` value. That's because their are included in the kit (for core plugins) or auto resolve (for local plugins). 

The `external` plugins have to specify their location with an url.

For `community` plugins, just prefix the plugin name with a `@` sign.

Depending on where the plugin live, you register it differently. We'll take `ga`  plugin (short for google analytics) as an exemple :

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

They have to be located in the `plugins` folder, inside the `kit_local` folder at the root of your kit folder. Ex: 

```text
📂 kit_folder
 ┃ 
 ┣ 📂 kit_local
 ┃ ┗ 📂 plugins
 ┃   ┗ 📄 some-local-plugin.js
 ┃ 
 ┣ 📄 index.html
 ┣ 📄 kitrc.json
 ┣ ...
```

### community plugins

It turns out the [[ga|ga]] plugin is an actual community plugin, that you can use right now. I would suggest adding this particular plugin in the global configuration file `kitrc.md`, so all your app can benefit from the tracking. 

```yaml
plugins:
  ga: "@ga"
```

You can of course, in any page, overide the global configuration or disable the plugin like so:

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

