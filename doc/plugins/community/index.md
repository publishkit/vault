---
title: Community Plugins
alias: Community Plugins
---
#  Plugins

```dataview
table without id link(file.link) as plugin, description
from "doc/plugins/community" 
where file.link != [[doc/plugins/community/index]]
sort file.name
```