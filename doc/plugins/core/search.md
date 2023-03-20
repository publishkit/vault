---
alias: $search
core: true
author: louis
description: Enable global full-text search
---
# search

> Enable global full-text search

## use

```yaml
plugins:
  search: true
```

## options

```yaml
search:
  chars: 3
  fuzzy: 0.2
  padding: 40
  max_results: 5
```

## methods

- `$search.search(query: string)`