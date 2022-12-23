---
core: true
---

About modals

modal call to action:
```html
<a href="#" role="button" class="contrast outline" 
   data-click="$('#modal-example').modal('open', event)">
	Open modal
</a>
```
modal element:
```html
<dialog id="modal-example">
  <article>
    <a href="#" class="close" 
	    data-click="$('#modal-example').modal('close', event)"></a>
    <h3>Confirm your action!</h3>
    <p>
      Cras sit amet maximus risus.<br/>Pellentesque sodales odio sit amet augue finibus pellentesque.<br/><br/>Nullam finibus risus non semper euismod.
    </p>
    <footer>
      <a href="#" role="button" class="secondary" 
        data-click="$('#modal-example').modal('close', event)">
        Cancel
      </a>
      <a href="#" role="button" 
        data-click="$('#modal-example').modal('close', event)">
        Confirm
      </a>
    </footer>
  </article>
</dialog>
```
