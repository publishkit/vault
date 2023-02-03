---
title: Demo
alias: $demo
---
# Demo

```dataview
table without id link(file.link, title) as name, description
from "demo" 
where file.link != [[demo/index]] 
and file.link != [[demo/dirrc]]
sort title
```