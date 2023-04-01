---
alias: $widget.card
---
# card

## basic

```markdown
<p data-card></p>

# my title
I'm **bold text** inside a `card` widget.

<p data-end></p>
```

<!-- preview --><p data-preview></p>
<h1 class="noprocess">my title</h1>

I'm **bold text** inside a `card` widget.

<!-- end:preview --><p data-end></p>


## style

You can style a card by using the `class` & `style` attribute.

```markdown
<p data-card 
   class="bg-primary text-white text-center py-4"
   style="border: 10px solid var(--contrast);"></p>

styled card

<p data-end></p>
```

<!-- card --><p data-card class="bg-primary text-white text-center py-4" style="border: 10px solid var(--contrast);"></p>

styled card

<!-- end:card --><p data-end></p>


## multi

Multi cards can be rendered from a simple markdown list.

```markdown
<p data-card class="grid-auto"></p>

-
  - ![[superman.png]]
  - ## Superman
-
  - <img src="attachements/batman.png" />
  - ## Batman
-
  - <img src="https://publishkit.dev/attachements/spiderman.png" />
  - ## Spiderman

<p data-end></p>
```

<!-- cards --><p data-card  class="grid-auto"></p>
- 
  - ![[superman.png]]
  - <h2 class="noprocess">Superman</h2>
- 
  - ![[batman.png]]
  - <h2 class="noprocess">Batman</h2>
- 
  - ![[spiderman.png]]
  - <h2 class="noprocess">Spiderman</h2>

<!-- end:cards --><p data-end></p>

You can style each item with:
- data-item-class
- data-item-style



## data-item-click

Add a click listener to each item list element. You have access to the current item, the index, and the items array.

```markdown
<p data-card data-item-click="$app.goto(item.href)"></p>

- Themes
	- href: [[doc/themes]]
	- <i class="bx bx-palette"></i>
- Plugins
	- href: doc/plugins
	- <i class="bx bxs-package"></i>
- Widgets
	- href: doc/widgets
	- <i class="bx bxs-widget"></i>

<p data-end></p>
```

<!-- cards --><p data-card class="grid-2 fixed center" data-item-class="cursor" data-item-click="$app.goto(item.href)"></p>
- Themes
	- href: [[doc/themes]]
	- <i class="bx bx-palette"></i>
- Plugins
	- href: doc/plugins
	- <i class="bx bxs-package"></i>
- Widgets
	- href: doc/widgets
	- <i class="bx bxs-widget"></i>

<!-- end:cards --><p data-end></p>
## data-href

Each card item content gets wrappred inside a link tag, pulling the value from the `href` props passed to each item of the list.

```markdown
<p data-card data-item-href></p>

- Themes
	- href: [[doc/themes]]
	- <i class="bx bx-palette"></i>
- Plugins
	- href: doc/plugins
	- <i class="bx bxs-package"></i>
- Widgets
	- href: doc/widgets
	- <i class="bx bxs-widget"></i>

<p data-end></p>
```

<!-- cards --><p data-card class="grid-2 fixed center" data-item-href></p>
- Themes
	- href: [[doc/themes]]
	- <i class="bx bx-palette"></i>
- Plugins
	- href: doc/plugins
	- <i class="bx bxs-package"></i>
- Widgets
	- href: doc/widgets
	- <i class="bx bxs-widget"></i>

<!-- end:cards --><p data-end></p>