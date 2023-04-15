---
title: Community Themes
alias: Community Themes
tags: [theme, community]
---
# Themes

```dataview
table without id link(file.link) as theme
from "doc/themes/community"
where file.link != [[doc/themes/community/index]] 
and file.link != [[doc/themes/community/dirrc]] 
sort file.name
```