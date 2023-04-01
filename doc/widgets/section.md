---
alias: $ui.section
---
# section

Sections are meant to be used with `layout.fluid`, and takes 100% of the width wiewport. You can wrap any markdown into a section:

```markdown
<p data-section class="gradient-bg text-white"></p>

# Basic section

Dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.

<p data-end></p>
```

<!-- section --><p data-section class="gradient-bg text-white mb-4"></p>
<h1 class="noprocess">Basic section</h1>

Dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
<!-- end:section --><p data-end></p>

## background

You can use the following classes:
- primary-bg
- secondary-bg
- gradient-bg

You can also specify the background color in the `data-bg` prop:

```markdown
<p data-section data-bg="red" class="text-white"></p>

red section

<p data-end></p>
```
<!-- section --><p data-section data-bg="red" class="text-white"></p>
red section
<!-- end:section --><p data-end></p>

## diagonal
<!-- section --><p data-section class="diagonal v1 primary-bg text-white my-4"></p>
class="diagonal v1 primary-bg text-white"
<!-- end:section --><p data-end></p>

<!-- section --><p data-section class="diagonal v2 primary-bg text-white my-4"></p>
class="diagonal v2 primary-bg text-white"
<!-- end:section --><p data-end></p>
## angle
<!-- section --><p data-section data-bg="" class="angle primary-bg text-white"></p>
class="angle v1 primary-bg text-white"
<!-- end:section --><p data-end></p>
<!-- section --><p data-section data-bg="" class="angle v2 primary-bg text-white"></p>
class="angle v2 primary-bg text-white"
<!-- end:section --><p data-end></p>
<!-- section --><p data-section data-bg="" class="angle v3 primary-bg text-white"></p>
class="angle v3 primary-bg text-white"
<!-- end:section --><p data-end></p>
<!-- section --><p data-section data-bg="" class="angle v4 primary-bg text-white"></p>
class="angle v4 primary-bg text-white"
<!-- end:section --><p data-end></p>
## waves
<!-- section --><p data-section class="waves primary-bg text-white"></p>
class="waves primary-bg text-white"
<!-- end:section --><p data-end></p>
## spikes
<!-- section --><p data-section class="spikes primary-bg text-white"></p>
class="spikes primary-bg text-white"
<!-- end:section --><p data-end></p>

