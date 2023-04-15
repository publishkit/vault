---
alias: $props
core: true
author: louis
description: Dynamic content bindings
tags: [plugin, core, props]
props:
  color: "red"
  counter: 1
  tickers: ["€", "¥"]
  total: "(price, qty, ticker='€') => (price * qty) + ticker"
  toggleColor: "() => { ~color = ~color == 'red' ? 'blue' : 'red' }"
  foo:
    bar: "baz"
---
# props

> The $props plugin makes markdown content fully dynamic and computable.



You can define any properties inside the `props` object of your frontmatter :

```yaml
props:
  counter: 1
  color: "red"
  tickers: ["€", "¥"]
  total: "(price, qty, ticker=0) => (price * qty) + ~tickers[ticker]"
  toggleColor: "() => { ~color = ~color == 'red' ? 'blue' : 'red' }"
  foo:
    bar: "baz"
```


## about

Props can:

- be of any types, even functions.
- be rendered anywhere in your markdown body, as long as they are single child of their parent element (paragraph, codeblocks, tables).
- be used as expressions in custom html attributes.
- be recognized by the kit by prefixing them with a `~`.

| markdown                  | prop value                | 
| ------------------------- | ------------------------- | 
| <span class="noprocess">~color</span>                  | `~color`                  |
| <span class="noprocess">~foo.bar</span>                  | `~foo.bar`                  |
| <span class="noprocess">~tickers[0]</span>                  | `~tickers[0]`                  |
| <span class="noprocess">~total(10, 3)</span>             | `~total(10, 3)`             |
| <span class="noprocess">~total(10, ~counter)</span>      | `~total(10, ~counter)`      |
| <span class="noprocess">~total(10, ~counter, "¥")</span> | `~total(10, ~counter, "¥")` |
| <span class="noprocess">~counter</span>                  | `~counter`                  |
| <span class="noprocess">~counter \* 2</span>             | `~counter * 2`              |

Props resolves to their litteral javascript value, so any valid javascript will work.

```js
~color.toUpperCase()
~foo.bar.replace("z", "zzz")
~tickers.includes("€")
~tickers.push("¥")
~counter * 2
~counter++
~total(10, ~counter) + " ttc"
```


## data-click

Use props inside click events:

```markdown
`counter` = <span>~counter</span>

<button data-click="~counter--">
  decrement
</button>
<button data-click="~counter++">
  increment
</button>
```

<!-- preview --><p data-preview></p>
`counter` = <span>~counter</span>

<button class="secondary outline me-2" data-click="~counter--">
<i class="bx bx-minus-circle me-2"></i>decrement
</button>
<button class="secondary outline" data-click="~counter++">
<i class="bx bx-plus-circle me-2"></i>increment
</button>

<!-- end:switch --><p data-end></p>



## data-bind

You can bind props to native html inputs and kit [[doc/widgets/index|widgets]]. 

- on an input:

```markdown
`foo.bar` = <span>~foo.bar</span>
<input type="text" data-bind="~foo.bar" />
```

<!-- preview --><p data-preview></p>
`foo.bar` = <span>~foo.bar</span>

<input type="text" data-bind="~foo.bar" />

<!-- end:preview --><p data-end></p>


- on a kit widget

```markdown
`color` = <span>~color</span>

<p data-switch data-bind="~color"></p>

- red
- blue

<p data-end></p>
```

<!-- preview --><p data-preview></p>
`color` = <span>~color</span>

<!-- switch --><p data-switch data-bind="~color"></p>
- red
- blue

<!-- end:switch --><p data-end></p>
<!-- end:preview --><p data-end></p>

## data-show

Display an element when a given condition is met:

```markdown
<button data-click="~toggleColor()" role="button">Toggle</button>
<span data-show="~color=='red'">red</span>
<span data-show="~color=='blue'">blue</span>
```

<!-- preview --><p data-preview></p>
<button data-click="~toggleColor()" role="button" class="d-inline m-0 me-4">Toggle</button><span data-show="~color=='red'">red</span><span data-show="~color=='blue'">blue</span>

<!-- end:preview --><p data-end></p>

