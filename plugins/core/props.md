---
alias: $props
core: true
author: louis
description: Dynamic content bindings
props:
  color: "red"
  counter: 1
  tickers: ["€", "¥"]
  total: "(price, qty, ticker='€') => (price * qty) + ticker"
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
counter = ~counter

<button data-click="~counter--">
  decrement
</button>
<button data-click="~counter++">
  increment
</button>
```

counter = <span>~counter</span>

<button class="secondary outline" data-click="~counter--">
<i class="bx bx-minus-circle me-2"></i>decrement
</button>
<button class="secondary outline" data-click="~counter++">
<i class="bx bx-plus-circle me-2"></i>increment
</button>



## data-ui

You can transform lists into specific ui components, by inserting a html `p` tag before the list, and specifying a `data-ui` component.

```markdown
<p data-ui="switch"></p>
- red
- blue
```

<!-- kit --><p data-ui="switch"></p>
- red
- blue

## data-bind

You can bind ui components to a props, so that it's stays in sync:

```markdown
<p data-ui="switch" data-bind="~color"></p>
- red
- blue
```

current `color` value = <span>~color</span>

<!-- kit --><p data-ui="switch" data-bind="~color"></p>
- red
- blue


## data-show

Display an element when a given condition is met:

```markdown
<span data-show="~color=='red'">red</span>
<span data-show="~color=='blue'">blue</span>
```

Ex: <span data-show="~color=='red'">red</span><span data-show="~color=='blue'">blue</span>

## lists

Basic list:

```markdown
- monthly
- yearly
```

```js
[
  { key: "monthly"},
  { key: "yearly"},
]
```

Detailed list:

```markdown
- monthly
  - label: <i class="bx bx-calendar me-2"></i>MONTHLY
- yearly
  - label: YEARLY <i class="bx bxs-gift ms-2" ></i>
```

```js
[
  { 
    key: "monthly", 
    label: "<i class='bx bx-calendar me-2'></i>MONTHLY"
  },
  { 
    key: "yearly", 
    label: "YEARLY <i class='bx bx-gift me-2'></i>"
  },
]
```
