:default
========

The `:default` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) selects form elements that are the
default in a group of related elements.

Try it
------

What this selector matches is defined in [HTML Standard §4.16.3
Pseudo-classes](https://html.spec.whatwg.org/multipage/semantics-other.html#selector-default)
--- it may match the
[`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button),
[`<input type="checkbox">`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/checkbox),
[`<input type="radio">`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/radio),
and
[`<option>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option)
elements:

- A default option element is the first one with the `selected`
    attribute, or the first enabled option in DOM order. `multiple`
    [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select)s
    can have more than one `selected` option, so all will match
    `:default`.
- `<input type="checkbox">` and `<input type="radio">` match if they
    have the `checked` attribute.
- [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button)
    matches if it is a
    [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form)\'s
    [default submission
    button](https://html.spec.whatwg.org/multipage/form-control-infrastructure.html#implicit-submission):
    the first `<button>` in DOM order that belongs to the form. This
    also applies to
    [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
    types that submit forms, like `image` or `submit`.

Syntax
------

[css]

```css
:default {
  /* ... */
}
```

Examples
--------

### HTML

[html]

```html
<fieldset>
  <legend>Favorite season</legend>

  <input type="radio" name="season" id="spring" value="spring" />
  <label for="spring">Spring</label>

  <input type="radio" name="season" id="summer" value="summer" checked />
  <label for="summer">Summer</label>

  <input type="radio" name="season" id="fall" value="fall" />
  <label for="fall">Fall</label>

  <input type="radio" name="season" id="winter" value="winter" />
  <label for="winter">Winter</label>
</fieldset>
```

### CSS

[css]

```css
input:default {
  box-shadow: 0 0 2px 1px coral;
}

input:default + label {
  color: coral;
}
```

### Result

Specifications
--------------

  ----------------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  selector-default]](https://html.spec.whatwg.org/multipage/semantics-other.html#selector-default)

[Selectors Level 4\
  [\# default-pseudo]](https://drafts.csswg.org/selectors/#default-pseudo)
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

`:default`

10

79

4

No

10

5

37

18

4

10.1

5

1.0

See also
--------

- [Web forms --- Working with user
    data](https://developer.mozilla.org/en-US/docs/Learn/Forms)
- [Styling web
    forms](https://developer.mozilla.org/en-US/docs/Learn/Forms/Styling_web_forms)
- Related HTML elements:
    [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button),
    [`<input type="checkbox">`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/checkbox),
    [`<input type="radio">`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/radio),
    and
    [`<option>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:default>
