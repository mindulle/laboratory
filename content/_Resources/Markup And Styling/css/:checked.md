:checked
========

The `:checked` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) selector represents any **radio**
([`<input type="radio">`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/radio)),
**checkbox**
([`<input type="checkbox">`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/checkbox)),
or **option**
([`<option>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option)
in a
[`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select))
element that is checked or toggled to an `on` state.

Try it
------

The user can engage this state by checking/selecting an element, or
disengage it by unchecking/deselecting the element.

**Note:** Because browsers often treat `<option>`s as [](replaced_element.md), the extent to which they can be styled with
the `:checked` pseudo-class varies from browser to browser.

Syntax
------

[css]

```css
:checked {
  /* ... */
}
```

Examples
--------

### Basic example

#### HTML

[html]

```html
<div>
  <input type="radio" name="my-input" id="yes" value="yes" />
  <label for="yes">Yes</label>

  <input type="radio" name="my-input" id="no" value="no" />
  <label for="no">No</label>
</div>

<div>
  <input type="checkbox" name="my-checkbox" id="opt-in" />
  <label for="opt-in">Check me!</label>
</div>

<select name="my-select" id="fruit">
  <option value="opt1">Apples</option>
  <option value="opt2">Grapes</option>
  <option value="opt3">Pears</option>
</select>
```

#### CSS

[css]

```css
div,
select {
  margin: 8px;
}

/* Labels for checked inputs */
input:checked + label {
  color: red;
}

/* Radio element, when checked */
input[type="radio"]:checked {
  box-shadow: 0 0 0 3px orange;
}

/* Checkbox element, when checked */
input[type="checkbox"]:checked {
  box-shadow: 0 0 0 3px hotpink;
}

/* Option elements, when selected */
option:checked {
  box-shadow: 0 0 0 3px lime;
  color: red;
}
```

#### Result

### Toggling elements with a hidden checkbox

This example utilizes the `:checked` pseudo-class to let the user toggle
content based on the state of a checkbox, all without using
[JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript).

#### HTML

[html]

```html
<input type="checkbox" id="expand-toggle" />

<table>
  <thead>
    <tr>
      <th>Column #1</th>
      <th>Column #2</th>
      <th>Column #3</th>
    </tr>
  </thead>
  <tbody>
    <tr class="expandable">
      <td>[more text]</td>
      <td>[more text]</td>
      <td>[more text]</td>
    </tr>
    <tr>
      <td>[cell text]</td>
      <td>[cell text]</td>
      <td>[cell text]</td>
    </tr>
    <tr>
      <td>[cell text]</td>
      <td>[cell text]</td>
      <td>[cell text]</td>
    </tr>
    <tr class="expandable">
      <td>[more text]</td>
      <td>[more text]</td>
      <td>[more text]</td>
    </tr>
    <tr class="expandable">
      <td>[more text]</td>
      <td>[more text]</td>
      <td>[more text]</td>
    </tr>
  </tbody>
</table>

<label for="expand-toggle" id="expand-btn">Toggle hidden rows</label>
```

#### CSS

[css]

```css
/* Hide the toggle checkbox */
#expand-toggle {
  display: none;
}

/* Hide expandable content by default */
.expandable {
  visibility: collapse;
  background: #ddd;
}

/* Style the button */
#expand-btn {
  display: inline-block;
  margin-top: 12px;
  padding: 5px 11px;
  background-color: #ff7;
  border: 1px solid;
  border-radius: 3px;
}

/* Show hidden content when the checkbox is checked */
#expand-toggle:checked ~ * .expandable {
  visibility: visible;
}

/* Style the button when the checkbox is checked */
#expand-toggle:checked ~ #expand-btn {
  background-color: #ccc;
}
```

#### Result

Specifications
--------------

  ----------------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  selector-checked]](https://html.spec.whatwg.org/multipage/semantics-other.html#selector-checked)

[Selectors Level 4\
  [\# checked]](https://drafts.csswg.org/selectors/#checked)
  ----------------------------------------------------------------------------------------------------------

Browser compatibility
---------------------

Desktop

Mobile

Chrome

Edge

Firefox

Internet Explorer

Opera

Safari

WebView Android

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

`:checked`

1On macOS, styling `<option>` elements has no effect.

12On macOS, styling `<option>` elements has no effect.

1\[\"From Firefox 56, `<option>` elements cannot be styled.\", \"On
macOS, styling `<option>` elements has no effect.\"\]

9

9On macOS, styling `<option>` elements has no effect.

3.1Styling `<option>` elements has no effect.

2

18

4From Firefox 56, `<option>` elements cannot be styled.

10.1

2Styling `<option>` elements has no effect.

1.0

See also
--------

- [Web forms --- working with user
    data](https://developer.mozilla.org/en-US/docs/Learn/Forms)
- [Styling web
    forms](https://developer.mozilla.org/en-US/docs/Learn/Forms/Styling_web_forms)
- Related HTML elements:
    [`<input type="checkbox">`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/checkbox),
    [`<input type="radio">`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/radio),
    [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select),
    and
    [`<option>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option)
- [Replaced elements](replaced_element.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:checked>
