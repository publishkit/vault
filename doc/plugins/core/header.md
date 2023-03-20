---
alias: $header
core: true
author: louis
description: Customize site header
---
# header

> Customize site header

## use

```yaml
plugins:
  header: true
```


## options

```yaml
header:
  name: SiteName
  name_fontsize: 0.8rem
  logo: http://epic.spb.ru/hero/hero.jpg
  logo_height: 40px
  fluid: false
```

| option      | desc                                                |
| ----------- | --------------------------------------------------- |
| name        | fallback to `site.name`. set to `false` to hide it. |
| name_fontsize   | adjust name font size |
| logo        | fallback to `site.logo`                             |
| logo_height | adjust logo height                                  |
| icons_fontsize | adjust icons font size                                  |
| fluid       | fluid layout (width=100%)                           |
