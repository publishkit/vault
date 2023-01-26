---
core: true
author: louis
description: Enable & create modals
---
# modals

> Enable & create modals

## use

```yaml
plugins:
  modal: true
```


## create

In any of your markdown file, add a modal & a call to action

call to action:

```html
<!-- A Tag (use return statement) -->
<a href="#" role="button" class="contrast outline" 
   data-click="return $modal.open('modal-example')">
	Open modal Link
</a>

<!-- or any other Tag (button, div, ...) -->
<button class="contrast outline" 
   data-click="$modal.open('modal-example')">
	Open modal Button
</button>
```

> [!info]
> When binding data-click to `<a/>` tag, you must add a `return` statement to prevent link to follow `href`. You can omit this statement in other tags.

modal element:

```html
<dialog id="modal-example">
  <article>
	<a href="#" class="close" 
	   data-click="return $modal.close()"></a>
	<h3>Confirm your action!</h3>
	<p>
	  Cras sit amet maximus risus.<br/>
	  Pellentesque sodales odio sit amet augue finibus pellentesque.<br/><br/> 
	  Nullam finibus risus non semper euismod.
	</p>
	<footer>
	  <button class="secondary" data-click="$modal.close()">
		Cancel
	  </button>
	  <button data-click="$modal.close()">
		Confirm
	  </button>
	</footer>
  </article>
</dialog>
```

## demo

<button class="contrast outline" data-click="$modal.open('modal-example')">Open modal</button>
<!-- Modal -->
<dialog id="modal-example">
  <article>
	<a href="#" class="close" data-click="return $modal.close()"></a>
	<h3>Confirm your action!</h3>
	<p>
	  Cras sit amet maximus risus.<br/>
	  Pellentesque sodales odio sit amet augue finibus pellentesque.<br/><br/> 
	  Nullam finibus risus non semper euismod.
	</p>
	<footer>
	  <button class="secondary" data-click="$modal.close()">
		Cancel
	  </button>
	  <button data-click="$modal.close()">
		Confirm
	  </button>
	</footer>
  </article>
</dialog>
