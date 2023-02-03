---
title: Blog
alias: $blog
---
# The Blog

```dataview
table without id link(file.link, title) as "", date as " "
from "blog" and -"blog/draft"
where file.link != [[blog/index]] 
and file.link != [[blog/dirrc]]
sort date
```