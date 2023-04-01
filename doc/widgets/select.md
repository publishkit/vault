---
alias: $widget.select
props:
  color: "red"
  colors: []
---
# select

```markdown
`color` = <span>~color</span>

<p data-select data-bind="~color"></p>

- red
- blue
- purple

<p data-end></p>
```

<!-- preview --><p data-preview></p>
`color` = <span>~color</span>

<!-- select --><p data-select data-bind="~color" placeholder="Pick color"></p>

- red
- blue
- purple

<!-- end:select --><p data-end></p>

<!-- end:preview --><p data-end></p>

Multi select by adding `multiple` prop to the widget:

```markdown
`colors` = <span>~colors</span>

<p data-select
   data-bind="~colors"
   multiple
   placeholder="Pick color"></p>

- red
- blue
- purple

<p data-end></p>
```

<!-- preview --><p data-preview></p>

`colors` = <span>~colors</span>

<!-- select-multi --><p data-select multiple data-bind="~colors" placeholder="Pick color"></p>

- red
- blue
- purple

<!-- end:select-multi --><p data-end></p>

<!-- end:preview --><p data-end></p>




