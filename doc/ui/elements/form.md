---
alias: $ui.form
tags: [ui, form]
---
# form

<div>
<fieldset>
<input type="text" value="" />
</fieldset>
<fieldset>
<input type="date" />
</fieldset>
<fieldset>
<input type="time" />
</fieldset>
<fieldset>
<input type="color" />
</fieldset>
<fieldset>
<input type="search" placeholder="search" />
</fieldset>

<!-- Select -->
<fieldset>
<select data-select placeholder="Select">
<option>Option 1</option>
<option>Option 2</option>
<option>Option 3</option>
</select>
</fieldset>

<!-- Multi Select -->
<fieldset>
<select data-select="" multiple placeholder="Multi Select">
<option>Option 1</option>
<option>Option 2</option>
<option>Option 3</option>
</select>
</fieldset>

<!-- Dropdown -->
<fieldset>
<details role="list">
  <summary aria-haspopup="listbox">Dropdown</summary>
  <ul role="listbox">
	<li><a href="#" data-click="return false">Action</a></li>
	<li><a href="#" data-click="return false">Another action</a></li>
	<li><a href="#" data-click="return false">Something else here</a></li>
  </ul>
</details>
</fieldset>

<!-- Radios -->
<fieldset>
<label for="small">
	<input type="radio" id="small" name="size" value="small" checked>
	radio
</label>
<label for="medium">
	<input type="radio" id="medium" name="size" value="medium">
	radio
</label>
<label for="extralarge">
	<input type="radio" id="extralarge" name="size" value="extralarge" disabled>
	disabled
</label>
</fieldset>

<!-- Checkboxes -->
<fieldset>
<label for="terms">
	<input type="checkbox" id="terms" name="terms">
	checkbox
</label>
<label for="terms_sharing">
	<input type="checkbox" id="terms_sharing" name="terms_sharing" disabled checked>
	disabled
</label>
</fieldset>

<!-- Switches -->
<fieldset>
<label for="switch">
	<input type="checkbox" id="switch" name="switch" role="switch">
	switch
</label>
</fieldset>



</div>

