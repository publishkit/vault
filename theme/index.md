---
alias: $theme
title: $theme
description: Configure theme
---
# theme

> Configure theme


## use

```yaml
plugins:
  theme: "@default"
```

## customize

```yaml
theme:
  darkmode: false
  primary: "#0f0"
  highlight: base16/green-screen
  font: monospace
  headings: 
    font: bungee-shade
```

## live demo

default theme:
- [@default|primary:green](theme?theme=@default|primary:green)
- [@default|primary:hex:0f0](theme?theme=@default|primary:hex:0f0)
- [@default|highlight:base16/green-screen](theme?theme=@default|highlight:base16/green-screen)
- [@default|headings.font:ResotERose](theme?theme=@default|headings.font:ResotERose)
- [@default|headings.font:Kiti Cuties](theme?theme=@default|headings.font:Kiti%20Cuties)

matrix theme:
- [@matrix](theme?theme=@matrix|primary:hex:0f0)
- [@matrix|primary:red](theme?theme=@matrix|primary:red)
- [@matrix|animate:false](theme?theme=@matrix|animate:false)