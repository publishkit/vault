---
title: Setup
alias: Setup
tags: [setup]
---
# Setup

```dataview
table without id link(file.link, title) as ""
from "doc/setup" 
where file.link != [[doc/setup/index]] 
and file.link != [[doc/setup/dirrc]]
sort title
```