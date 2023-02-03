---
alias: $ui.form
---
# form

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

