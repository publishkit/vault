---
title: Themes
alias: Themes, $themes
description: Play with themes
---
# Themes

UI & UX is at the core of this project. You can use the default or the [[community]] themes, and adjust to your preferences through high level options.

```yaml
# @file=kitc.md
# register theme
plugins:
  theme: "@default"


# custom options
theme:
  highlight: base16/green-screen
  primary: "#0f0"
  font: monospace
  headings: 
    font: bungee-shade
```

- Checkout the [[doc/themes/community/index|Community Themes]]
- [[doc/themes/create|Create your theme]], it's a piece of cake 🍰

## options

### highlight

Highlight codeblocks with 197 languages and 248 styles from [highlightjs.org](https://highlightjs.org/)

- [@default|highlight:Far](doc/themes?theme=@default|highlight:Far#heading-highlight)
- [@default|highlight:Base16 / Icy Dark](doc/themes?theme=@default|highlight:Base16%20/%20Icy%20Dark#heading-highlight)
- [@default|highlight:base16/green-screen](doc/themes?theme=@default|highlight:base16/green-screen#heading-highlight)

Demo:

```markdown
# hello world

you can write text [with links](http://example.com) inline or [link references][1].

* one _thing_ has *em*phasis
* two __things__ are **bold**

[1]: http://example.com

---

hello world
===========

<this_is inline="xml"></this_is>

> markdown is so cool

    so are code segments

1. one thing (yeah!)
2. two thing `i can write code`, and `more` wipee!
```

### primary

Primary site color.

- [@default|primary:orange](doc/themes?theme=@default|primary:orange#heading-primary)
- [@default|primary:hex:0f0](doc/themes?theme=@default|primary:hex:0f0#heading-primary)

### font

Choose any of the 20k fonts from [cdnfonts.com](https://www.cdnfonts.com/)

- [@default|font:Carleton](doc/themes?theme=@default|font:Carleton#heading-font)
- [@default|font:One Day](doc/themes?theme=@default|font:One%20Day#heading-font)
- [@default|font:Apes On Parade](doc/themes?theme=@default|font:Apes%20On%20Parade#heading-font)
- [@default|font:KG Makes You Stronger ](doc/themes?theme=@default|font:KG%20Makes%20You%20Stronger#heading-font)



### headings

By default headings inherits the `font` and `color` option. 

- [@default|headings.font:Kiti Cuties](doc/themes?theme=@default|headings.font:Kiti%20Cuties#heading-headings)
- [@default|headings.color:darkorange](doc/themes?theme=@default|headings.color:darkorange#heading-headings)


