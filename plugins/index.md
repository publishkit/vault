---
title: Plugins
alias: Plugins
---
# Plugins

Plugins are PublishKit building blocks. Everything on the page that is not the "actual content" is defacto rendered by a plugin.

There are no limits except imagination on what a plugin can do. PublishKit provides some `core` plugins out of the box. Other plugins are delivered by the community.

- [[plugins/core/index|Core Plugins]]
- [[plugins/community/index|Community Plugins]]
- [[create|How to create a plugin]]


## usage

To use a plugin, open your [[doc/pkrc|pkrc]] file and in the `plugins` section, add a new entry with the id of the plugin set to `true`.

```yaml
plugins:
  plugin1: true
  plugin2: true
  plugin3: true
```

> [!tip]
> You can temporaly disable a plugin by setting a `false` value. Or remove it completely.

## options

Some plugins have options. To configure them, add a new entry at the root of your [[doc/pkrc|pkrc]] file with the plugin id, then add key values for the options.

```yaml
plugin1:
  option1: "foo"
  option2: ["bar", "baz"]
```

## overriding

Remember that each setting in your [[doc/pkrc|pkrc]] file can be overrided on a file or directory basis. This let you have a global site configuration via the `pkrc`, and fine tune any page of your site.

Let's say you want to activate `plugin1` on the entire site, except on your contact page. You will set your `pkrc` like:

```yaml
plugins:
  plugin1: true

plugin1:
  option1: "foo"
  option2: ["bar", "baz"]
```

and in your `contact.md` frontmatter:

```yaml
plugins:
  plugin1: false
```

Now if you just want to change `plugin1` options and not disable it, in `contact.md`:

```yaml
plugin1:
  option1: "new value"
```

Given the above `pkrc` configuration, and the overrided options in `contact.md`, the final options for `plugin1` will be:

```js
{
  option1: "new value"
  option2: ["bar", "baz"]
}
```