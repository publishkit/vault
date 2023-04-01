---
title: Widgets
alias: $widgets
props:
  name: "Bruce Wayne"
  color: "red"
  colors: []
---
# Widgets

The kit provides customisable widgets to enhance your content. Just include the widget in your markdown and give it some options.

## use

Wrap any markdown content around 2 `p` html tags. The opening tag defines the widget, as a `data-attribute`, and the closing tag use the `data-end` attribute.

```markdown
<p data-card></p>

# Some title

And some **bold** text inside a `card` widget !

<p data-end></p>
```

<!-- preview --><p data-card></p>
<h1 class="noprocess">Some title</h1>

And some **bold** text inside a `card` widget !

<!-- end:preview --><p data-end></p>

## configure

You can configure widgets via html [data-attributes](https://www.w3schools.com/tags/att_data-.asp) and first level attributes like `class` & `style`. For exemple, the [[doc/widgets/card|card]] widget let you quick set a background color via the `data-bg` attribute:

```markdown
<p data-card 
   data-bg="var(--contrast)" 
   class="text-white py-5"></p>

padded *white* text in a `contrast` background card

<p data-end></p>
```

<!-- preview --><p data-preview data-bg="var(--contrast)" class="text-white py-5"></p>
padded *white* text in a `contrast` background card

<!-- end:preview --><p data-end></p>

## dataset

Some widgets takes a predefined dataset as an argument, that you can pass via:

- the `data-set` attribute:

*Not yet implemented*

```markdown
<p data-card 
   data-set='[{key:"foo"}, {key:"bar"}, {key:"baz"}]'></p>
<p data-end></p>
```

- a markdown list inside the wrapped widget tags:
```markdown
<p data-card class="grid-auto fixed text-center"></p>

- foo
- bar
- baz

<p data-end></p>
```

<!-- cards --><p data-card class="grid-auto fixed text-center"></p>
- foo
- bar
- baz

<!-- end:cards --><p data-end></p>

---

The kit can transform a markdown list into a javascript array.

```markdown
- foo
- bar
```

```js
[
  { key: "foo"},
  { key: "bar"},
]
```

Detailed list:

```markdown
- foo
  - name: Foo<strong>Foo</strong>
  - age: 35
- bar
  - name: Bar<strong>Bar</strong>
  - age: 64
```

```js
[
  { 
    key: "foo", 
    name: "Foo<strong>Foo</strong>",
    age: 35
  },
  { 
    key: "bar", 
    name: "Bar<strong>Bar</strong>",
    age: 64
  },
]
```


# Widget

- [input](doc/widgets#heading-input)
- [select](doc/widgets#heading-select)
- [switch](doc/widgets#heading-switch)
- [section](doc/widgets#heading-section)
- [card](doc/widgets#heading-card)

![[input]]

![[switch]]

![[select]]

![[section]]

![[doc/widgets/card]]