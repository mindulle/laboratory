:focus-within
=============

The `:focus-within`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) matches an element if the element or any
of its descendants are focused. In other words, it represents an element
that is itself matched by the [`:focus`](:focus) pseudo-class or has a
descendant that is matched by `:focus`. (This includes descendants in
[shadow
trees](https://developer.mozilla.org/en-US/docs/Web/API/Web_components/Using_shadow_DOM).)

Try it
------

This selector is useful, to take a common example, for highlighting an
entire
[`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form)
container when the user focuses on one of its
[`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
fields.

Syntax
------

[css]

```css
:focus-within {
  /* ... */
}
```

Examples
--------

In this example, the form will receive special coloring styles when
either text input receives focus.

### HTML

[html]

```html
<p>Try typing into this form.</p>

<form>
  <label for="given_name">Given Name:</label>
  <input id="given_name" type="text" />
  <br />
  <label for="family_name">Family Name:</label>
  <input id="family_name" type="text" />
</form>
```

### CSS

[css]

```css
form {
  border: 1px solid;
  color: gray;
  padding: 4px;
}

form:focus-within {
  background: #ff8;
  color: black;
}

input {
  margin: 4px;
}
```

### Result

Specifications
--------------

  ------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------

  [Selectors Level 4\
  [\#
  the-focus-within-pseudo]](https://drafts.csswg.org/selectors/#the-focus-within-pseudo)

  ------------------------------------------------------------------------------------------------

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

`:focus-within`

60

79

52

No

47

10.1

60

60

52

44

10.3

8.0

See also
--------

- [`:focus`](:focus)
- [`:focus-visible`](:focus-visible)
- [Grab your user\'s attention with the focus-within
    selector](https://dev.to/vtrpldn/grab-your-user-s-attention-with-the-focus-within-css-selector-4d4)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:focus-within>
