---
alias: $search
core: true
author: louis
description: Enable global full-text search
tags: [plugin, core, search]
---
# search

> Enable global full-text search

This plugin let you search and navigate into your content, and will match any text found in page titles, headings or paragraphs.

## use

```yaml
plugins:
  search: true
```

## options

```yaml
search:
  shortcut: "command+k"
  placeholder: "Search..."
  chars: 3
  fuzzy: 0.2
  padding: 40
  max_results: 5
```

## methods

- `$search.search(query: string)`