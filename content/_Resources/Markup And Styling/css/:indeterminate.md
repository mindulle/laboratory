:indeterminate
==============

The `:indeterminate`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) represents any form element whose state
is indeterminate, such as checkboxes which have their HTML
[`indeterminate`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/checkbox#indeterminate_state_checkboxes)
attribute set to `true`, radio buttons which are members of a group in
which all radio buttons are unchecked, and indeterminate
[`<progress>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/progress)
elements.

[css]

```css
/* Selects any <input> whose state is indeterminate */
input:indeterminate {
  background: lime;
}
```

Elements targeted by this selector are:

- [`<input type="checkbox">`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/checkbox)
    elements whose `indeterminate` property is set to `true` by
    [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
- [`<input type="radio">`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/radio)
    elements, when all radio buttons with the same `name` value in the
    form are unchecked
- [`<progress>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/progress)
    elements in an indeterminate state

Syntax
------

```
:indeterminate
```

Examples
--------

### Checkbox & radio button

This example applies special styles to the labels associated with
indeterminate form fields.

#### HTML

[html]

```html
<fieldset>
  <legend>Checkbox</legend>
  <div>
    <input type="checkbox" id="checkbox" />
    <label for="checkbox">This checkbox label starts out lime.</label>
  </div>
</fieldset>

<fieldset>
  <legend>Radio</legend>
  <div>
    <input type="radio" id="radio1" name="radioButton" value="val1" />
    <label for="radio1">First radio label starts out lime.</label>
  </div>
  <div>
    <input type="radio" id="radio2" name="radioButton" value="val2" />
    <label for="radio2">Second radio label also starts out lime.</label>
  </div>
</fieldset>
```

#### CSS

[css]

```css
input:indeterminate + label {
  background: lime;
}
```

#### JavaScript

[js]

```js
const inputs = document.getElementsByTagName("input");

for (let i = 0; i < inputs.length; i++) {
  inputs[i].indeterminate = true;
}
```

#### Result

### Progress bar

#### HTML

[html]

```html
<progress></progress>
```

#### CSS

[css]

```css
progress {
  margin: 4px;
}

progress:indeterminate {
  width: 80vw;
  height: 20px;
}
```

#### Result

Specifications
--------------

  ----------------------------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  selector-indeterminate]](https://html.spec.whatwg.org/multipage/semantics-other.html#selector-indeterminate)

[Selectors Level 4\
  [\# indeterminate]](https://drafts.csswg.org/selectors/#indeterminate)
  ----------------------------------------------------------------------------------------------------------------------

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

`:indeterminate`

1

12

2

10

9

3

≤37

18

4

10.1

1

1.0

`checkbox`

1

12

3.6

10

10.6

3

≤37

18

4

11

1

1.0

`progress`

6

12

6

10

15

5.1

37

18

6

14

5

1.0

`radio`

39

79

51

No

26

10

39

39

51

26

10

4.0

See also
--------

- [Web forms --- Working with user
    data](https://developer.mozilla.org/en-US/docs/Learn/Forms)
- [Styling web
    forms](https://developer.mozilla.org/en-US/docs/Learn/Forms/Styling_web_forms)
- The
    [`<input type="checkbox">`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/checkbox)
    element\'s
    [`indeterminate`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/checkbox#indeterminate_state_checkboxe)
    attribute
- [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
    and the
    [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement)
    interface which implements it.
- The [`:checked`](:checked) CSS selector lets you style checkboxes
    based on whether they\'re checked or not

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:indeterminate>
