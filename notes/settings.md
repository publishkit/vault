---
alias: pkrc
---

# Settings

Global settings are located in the `pkrc` file at the root of your vault. Settings are just [frontmatter](https://help.obsidian.md/Advanced+topics/YAML+front+matter) variables.


> [!info] 
> - Each setting can be overrided on a page basis.
> - When you edit a setting, you have to re export your file.

## general
```yaml
pk_folder: /Users/louis/sites/PublishKit
site_id: insert_your_id
site_name: PublishKit
site_assets: /assets
description: Welcome to PublishKit
```


## layout
```yaml
fluid: false
header: true
footer: true
toc: true
rtoc: true
```

## search
```yaml
search: true
search_chars: 3
search_fuzzy: 0.2
search_padding: 20
search_max_results: 5
```

## social
```yaml
social_github: https://github.com/username
social_twitter:
social_twitch:
social_facebook:
social_instagram:
social_reddit:
social_linkedin:
```

## other
```yaml

# show frontmatter
frontmatter: false

# pdf options
pdf_notoolbar: false

# not yet implemented
breadcrumbs: false
latex: false
```


## styles

### css

You can override css variables.

```yaml
--font-family: Cousine, sans-serif
--primary: '#0ed519'
--primary-hover: '#0bb714'
```

> [!info]
> You can choose any fonts from [cdnfonts.com](https://www.cdnfonts.com/)
> Go to the font page that you like, for exemple [this one](https://www.cdnfonts.com/ambery-garden.font). 
> `font-family: 'Ambery Garden', sans-serif;`
> 
>Make sure you remove the quotes `'`  and the `;` 
> 
>```yaml
>--font-family: Ambery Garden, sans-serif
>```

### codeblocks

You get syntax highlighting out of the box with [highlight.js](https://highlightjs.org/) 
You can choose from the available themes [here](https://cdn.jsdelivr.net/gh/highlightjs/cdn-release@11.7.0/build/styles/).
```yaml
highlightjs: arta
```