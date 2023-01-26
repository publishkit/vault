---
---
# html showcase

## typography

<article aria-label="Inline text examples"><div class="grid"><div><p><abbr title="Abbreviation">Abbr.</abbr> <code>abbr</code></p><p><strong>Bold</strong> <code>strong</code> <code>b</code></p><p><em>Italic</em> <code>i</code> <code>em</code> <code>cite</code></p><p><del>Deleted</del> <code>del</code></p><p><ins>Inserted</ins> <code>ins</code></p><p><kbd>Ctrl + S</kbd> <code>kbd</code></p></div><div><p><mark>Highlighted</mark> <code>mark</code></p><p><s>Strikethrough</s> <code>s</code></p><p><small>Small </small><code>small</code></p><p>Text <sub>Sub</sub> <code>sub</code></p><p>Text <sup>Sup</sup> <code>sup</code></p><p><u>Underline</u> <code>u</code></p></div></div></article>

Find out more about fonts [[fonts|here]].

## callouts

> [!info]-
> **type**: note,info,todo

> [!tip]-
> **type**: tip,hint,important

> [!success]-
> **type**: success,check,done

> [!question]-
> **type**: question,help,faq

> [!warning]-
> **type**: warning,caution,attention

> [!danger]-
> **type**: danger,error,bug,failure,fail,missing

> [!quote]-
> **type**: quote,cite



## quote

> This is Quote



## headings

<article>
<h1 style="margin:0;">this is h1</h1>
<h2 style="margin:0;">this is h2</h2>
<h3 style="margin:0;">this is h3</h3>
<h4 style="margin:0;">this is h4</h4>
<h5 style="margin:0;">this is h5</h5>
</article>


## codeblock

```js
const foo = "bar,baz".split(',')[0]
```

Find out about code highlight [[highlight|here]].

## icons

Choose any of the 1634 open source icons from [boxicons](https://boxicons.com/).

```html
<i class='bx bxs-plane bx-xs'></i>
<i class='bx bxs-plane bx-sm'></i>
<i class='bx bxs-plane bx-md'></i>
<i class='bx bxs-plane bx-lg'></i>
```

<!-- Icons below -->
<div class="d-flex align-items-center">
<i class='bx bxs-plane bx-xs'></i>
<i class='bx bxs-plane bx-sm'></i>
<i class='bx bxs-plane bx-md'></i>
<i class='bx bxs-plane bx-lg'></i>
</div>


## image

![[showcase-image.jpg||300]]

## table 

| File             | type    | memory | ip           |
| ---------------- | ------- | ------ | ------------ |
| freebox 💻       | box     | -      | -            |
| macbook pro 💻   | laptop  | 16GB   | 192.168.0.12 |
| mac studio 💻    | mac     | 32GO   | 192.168.0.13  |
| nas 💻           | nas     | -      | 192.168.0.14 |
| HP Serie 🖨 | printer | -      | -            |
| ipad air 📱      | ipad    | 64GO   | -            |
| iphone 14 📱     | iphone  | 256GO  | -            |
| iphone SE 📱     | iphone  | 64GO   | -            |
| iphone 11 📱     | iphone  | -      | -            |
| Eyecloud 📹      | cam     | 168GO  | -            |
| reolink 4G 📹    | cam     | -      | -            |
| hikvision 📹     | cam     | -      | -            |
| amcrest 📹       | cam     | -      | 192.168.1.15 |


## modal

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

Find out more about modals [[modal|here]].

## forms

<div>
<input type="text" value="foobar" />
<input type="date" />
<input type="time" />
<input type="color" />
<input type="search" value="foobar" />
<select>
<option value="" selected>Select a fruit…</option>
<option>…</option>
<option>…</option>
</select>
<details role="list">
  <summary aria-haspopup="listbox">Dropdown</summary>
  <ul role="listbox">
	<li><a href="#">Action</a></li>
	<li><a href="#">Another action</a></li>
	<li><a href="#">Something else here</a></li>
  </ul>
</details>
<!-- Radios -->
<fieldset>
<legend>Size</legend>
<label for="small">
	<input type="radio" id="small" name="size" value="small" checked>
	Small
</label>
<label for="medium">
	<input type="radio" id="medium" name="size" value="medium">
	Medium
</label>
<label for="large">
	<input type="radio" id="large" name="size" value="large">
	Large
</label>
<label for="extralarge">
	<input type="radio" id="extralarge" name="size" value="extralarge" disabled>
	Extra Large
</label>
</fieldset>

<!-- Checkboxes -->
<fieldset>
<label for="terms">
	<input type="checkbox" id="terms" name="terms">
	I agree 
</label>
<label for="terms_sharing">
	<input type="checkbox" id="terms_sharing" name="terms_sharing" disabled checked>
	I agree 
</label>
</fieldset>

<!-- Switches -->
<fieldset>
<label for="switch">
	<input type="checkbox" id="switch" name="switch" role="switch">
	Publish on my profile
</label>
<label for="switch_disabled">
	<input type="checkbox" id="switch_disabled" name="switch_disabled" role="switch_disabled" disabled checked>
	User must change 
</label>
</fieldset>
</div>


## pdf

![[showcase-pdf.pdf]]

Find out more about pdfs [[pdf|here]].

## background
<div>
<div class="p-1 px-2 mb-1 bg-primary">.bg-primary</div>
<div class="p-1 px-2 mb-1 bg-secondary">.bg-secondary</div>
<div class="p-1 px-2 mb-1 bg-success">.bg-success</div>
<div class="p-1 px-2 mb-1 bg-danger">.bg-danger</div>
<div class="p-1 px-2 mb-1 bg-warning">.bg-warning</div>
<div class="p-1 px-2 mb-1 bg-info">.bg-info</div>
<div class="p-1 px-2 mb-1 bg-white">.bg-white</div>
<div class="p-1 px-2 mb-1 bg-black">.bg-black</div>
</div>
<p></p>

## latex

$$
y = \frac{1}{x}
$$


