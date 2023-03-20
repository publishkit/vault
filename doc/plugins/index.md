---
title: Plugins
alias: Plugins, $plugins
description: Plugins
---
# Plugins

Everything on the page that is not the "actual content" is rendered by a plugin.

Plugins are the Kit core design. Without any plugins, content is rendered as is, without any transformations, onto the page. But with plugins, that's where the magic begins. Plugins can do anything, from fully tweaking and theming the UI, to creating and binding UI elements, or just exposing functions for other plugins to consume. The Kit comes equipped with some `core` plugins out of the box. Other plugins are imagined and delivered by the `community`.

<!-- cards --><p data-card class="grid-2 fixed center" data-item-href="item.href + 'foo'"></p>
- Core Plugins
	- href: [[doc/plugins/core/index|Core Plugins]]
	- <i class="bx bxs-package bx-md mt-2"></i>
- Community Plugins
	- href: [[doc/plugins/community/index|Community Plugins]]
	- <i class="bx bx-group bx-md mt-2"></i>

<!-- end:cards --><p data-end></p>

## usage

Plugins can be added and overrided, taking precedence, in the frontmatter of the following files:
- the `kitrc.md` - [[doc/services/kitrc|kitrc]]
- any `dirrc.md` file in any directory
- individual markdown files
- in url - (aka url injection)

To register a plugin, in the frontmatter of the files mentioned above, add a key value pair under the `plugins` YAML object. Use the plugin name for the key, and set a `true` value. Ex:

```yaml
plugins:
  header: true
  navbar: true
  darkmode: true
```

---

Plugins can come from different places, they can be:

<!-- cards --><p data-card class="grid-2 center"></p>

- core
- local
- community
- external

<!-- end:cards --><p data-end></p>

Only **core** and **local** plugins can register by simply specifying a `true` value. That's because they are included in the kit (for core plugins) or auto resolve (for local plugins). 

The **community** plugins can be included by prefixing the name with a `@` sign. The **external** plugins just have to specify their location with a URL.

So, depending on where the plugin lives, you will register it differently. Example with the `ga`  plugin:

```yaml
plugins:
  # core & local
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

It turns out the [[ga|ga]] plugin is an actual community plugin, that you can use right now. I would suggest adding this particular plugin in your [[doc/services/kitrc|kitrc]], so all your pages can benefit from the tracking. 

```yaml
plugins:
  ga: "@ga"
```

You can of course, in any of your pages, override or disable the plugin:

```yaml
plugins:
  ga: false
```

## options

Plugins can have options. For example, the `ga` community plugin takes a Google tracking `id`. At the root of the frontmatter, create a YAML object with the plugin name, and provide the option in a `key: value` way:

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

For single option plugins, short syntax can be used:

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
await ui.render();
await plugins.transform();
await plugins.style();
await ui.draw();
await plugins.bind();
```

In fact, those are the 8 lines of code that compose the `kit` main function. Plugins can implement any of the following methods of the lifecycle:

- `init`
- `deps`
- `render`
- `transform`
- `style`
- `bind`

You can find a more details about each life cycle here: [[doc/plugins/create|Create a plugin]].

## more

Create your own plugin now ! - [[doc/plugins/create|Create a plugin]]

> [!note] 
> - Each plugin is exposed globally by it's name prefixed by a `$`. 
> - Interacting with a plugin is as simple as `$navbar.toggle()` or `$stripe.pay()`.
> 