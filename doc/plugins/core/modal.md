---
alias: $modal
core: true
author: louis
description: Use modals
---
# modals

> Use modals

*The modal plugin is registered by default, you can't turn it off.*

## use

Modal can be manualy added inside content, or programmatically created via plugins.

### in content

In the markdown file add a call to action, using any tag you want.

```html
<!-- Link Tag (use return statement) -->
<a href="#" 
   role="button" 
   class="contrast outline" 
   data-click="return $modal.open('modal-example')">
	Open modal Link
</a>

<!-- or any other Tag (button, div, ...) -->
<button 
  class="primary" 
  data-click="$modal.open('modal-example')">
	Open modal Button
</button>
```

> [!info]
> When binding data-click to an `<a/>` tag, you must add a `return` statement to prevent link to follow `href`. You can omit this statement in other tags.

add the modal:

```html
<dialog id="modal-example">
  <article>
	<a href="#" 
	   class="close" 
	   data-click="return $modal.close()"></a>
	   
	<h2>Modal Title!</h2>
	
	<p>
	  Cras sit amet maximus risus.<br/>
	  Pellentesque sodales odio sit amet augue finibus pellentesque.
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

### in plugin

```js
ui.addModal()
```


## demo

<button class="contrast outline" data-click="$modal.open('modal-example')">Open modal</button>
<!-- Modal -->
<dialog id="modal-example">
  <article>
	<a href="#" class="close" data-click="return $modal.close()"></a>
	<h2 class="noprocess">Modal Title!</h2>
	<p>
	  Cras sit amet maximus risus.<br/>
	  Pellentesque sodales odio sit amet augue finibus pellentesque.
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

