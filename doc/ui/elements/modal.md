---
alias: $ui.modal
---
# modal

<button class="contrast outline" data-click="$modal.open('modal-example')">Open modal</button>
<!-- Modal -->
<dialog id="modal-example">
  <article>
	<a href="#" class="close" data-click="return $modal.close()"></a>
	<h1 class="noprocess">Confirm your action!</h1>
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

checkout the [[doc/plugins/core/modal|$modal]] plugin!