---
title: Core Plugins
alias: Core Plugins
---
# Core plugins

```dataview
table without id "$"+link(file.link) as plugin, description
from "plugins/core"
where file.link != [[plugins/core/index]]
sort file.name
```