HTML attribute: size
====================

The `size` attribute defines the width of the
[`<input>`](../element/input) and the height of the
[`<select>`](../element/select) element. For the `input`, if the `type`
attribute is [text](../element/input/text) or
[password](../element/input/password) then it\'s the number of
characters. This must be an integer value of 0 or higher. If no `size`
is specified, or an invalid value is specified, the input has no size
declared, and the form control will be the default width based on the
user agent. If CSS targets the element with properties impacting the
width, CSS takes precedence.

The `size` attribute has no impact on constraint validation.

Try it
------

Examples
--------

By adding `size` on some input types, the width of the input can be
controlled. Adding size on a select changes the height, defining how
many options are visible in the closed state.

[html]

```html
<label for="fruit">Enter a fruit</label>
<input type="text" size="15" id="fruit" />
<label for="vegetable">Enter a vegetable</label>
<input type="text" id="vegetable" />

<select name="fruits" size="5">
  <option>banana</option>
  <option>cherry</option>
  <option>strawberry</option>
  <option>durian</option>
  <option>blueberry</option>
</select>

<select name="vegetables" size="5">
  <option>carrot</option>
  <option>cucumber</option>
  <option>cauliflower</option>
  <option>celery</option>
  <option>collard greens</option>
</select>
```

Specifications
--------------

**No specification found**

No specification data found for `html.elements.attribute.size`.\
[Check for problems with this page](#on-github) or contribute a missing
`spec_url` to
[mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).
Also make sure the specification is included in
[w3c/browser-specs](https://github.com/w3c/browser-specs).

Browser compatibility
---------------------

See also
--------

- [`maxlength`](maxlength)
- [`minlength`](minlength)
- [`pattern`](pattern)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/size>>
