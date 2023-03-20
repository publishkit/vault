---
title: Services
alias: Services
---
# services

```dataview
table without id link(file.link, title) as "", description as " "
from "doc/services" 
where file.link != [[doc/services/index]] 
and file.link != [[doc/services/dirrc]]
sort title
```