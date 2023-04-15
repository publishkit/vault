---
alias: $widget.input
tags: [widget, input]
props:
  name: "Bruce Wayne"
---
# input

```markdown
`name` = <span>~name</span>
<input type="text" data-bind="~name" />
```

<!-- preview --><p data-preview></p>
`name` = <span>~name</span>

<input type="text" data-bind="~name" />

<!-- end:preview --><p data-end></p>

> [!tip] Debounce
>  You can debounce by passing a a delay in the `data-debounce="700"` attribute.