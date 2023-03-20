---
title: Core Plugins
alias: Core Plugins
---
# Core plugins

```dataview
table without id link(file.link) as plugin, description
from "doc/plugins/core"
where file.link != [[doc/plugins/core/index]]
sort file.name
```