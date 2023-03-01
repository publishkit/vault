---
title: Community Plugins
alias: Community Plugins
---
# Community plugins

```dataview
table without id link(file.link) as plugin, description
from "plugins/community"
where file.link != [[plugins/community/index]]
sort file.name
```