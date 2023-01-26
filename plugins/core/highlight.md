---
core: true
author: louis
description: Highlight code blocks
---
# highlight

> This plugin enable highlight of code blocks

Choose from more then 197 languages and 248 styles from [highlightjs.org](https://highlightjs.org/static/demo)

## use

```yaml
plugins:
  highlight: true
```

## options

```yaml
highlight:
  theme: shades-of-purple
```

You can find themes name [here](https://github.com/highlightjs/cdn-release/tree/main/build/styles). If you use a base16 theme, make sure you prefix the theme name `theme: base16/green-screen`.

## preview

- [base16/green-screen](plugins/core/highlight?p=highlight|theme:base16/green-screen)
- [shades-of-purple](plugins/core/highlight?p=highlight|theme:shades-of-purple)
- [monokai](plugins/core/highlight?p=highlight|theme:monokai)
- [tomorrow-night-bright](plugins/core/highlight?p=highlight|theme:tomorrow-night-bright)