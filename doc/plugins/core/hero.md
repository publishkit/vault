---
alias: $hero
core: true
author: louis
description: Add a hero banner
tags: [plugin, core, hero]
---
# hero

> Add a hero banner

## use

```yaml
plugins:
  hero: true
```


## options

```yaml
hero:
  image: https://someurl.com
  height: 300px
```

- If you register the plugin without the image option, the pugin will look for an image in the top level `image` variable in your `kitrc`. If no image found, then plugin won't register.


## preview

- [p=hero|image:attachements/og-image.png](doc/plugins/core/hero.html?p=hero|image:attachements/og-image.png)
- [p=hero|image:https://unsplash.com/foo.png](doc/plugins/core/hero.html?p=hero|image:https://images.unsplash.com/photo-1507608869274-d3177c8bb4c7?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1170&q=80,height:400px)
- [p=hero|image:https://unsplash.com/bar.png](doc/plugins/core/hero.html?p=hero|image:https://images.unsplash.com/photo-1498673394965-85cb14905c89?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=870&q=80)

