:modal
======

The `:modal` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) matches an element that is in a state in
which it excludes all interaction with elements outside it until the
interaction has been dismissed. Multiple elements can be selected by the
`:modal` pseudo-class at the same time, but only one of them will be
active and able to receive input.

Try it
------

Syntax
------

[css]

```css
:modal {
  /* ... */
}
```

Usage notes
-----------

Examples of elements that will prevent user interaction with the rest of
the page and will be selected by the `:modal` pseudo-class include:

- The
    [`dialog`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dialog)
    element opened with the `showModal()` API.
- The element selected by the [`:fullscreen`](:fullscreen)
    pseudo-class when opened with the `requestFullscreen()` API.

Examples
--------

### Styling a modal dialog

This example styles a modal dialog that opens when the \"Update
details\" button is activated. This example has been built on top of the
[`<dialog>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dialog)
element
[example](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dialog#advanced_example).

#### CSS

[css]

```css
:modal {
  border: 5px solid red;
  background-color: yellow;
  box-shadow: 3px 3px 10px rgba(0 0 0 / 0.5);
}
```

### Result

Specifications
--------------

  ------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------

  [Selectors Level 4\
  [\#
  modal-state]](https://drafts.csswg.org/selectors/#modal-state)

  ------------------------------------------------------------------------

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

`:modal`

105

105

103

No

91

15.6

105

105

103

72

15.6

20.0

See also
--------

- [`dialog`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dialog)
    element
- Other element display state pseudo-classes:
    [`:fullscreen`](:fullscreen) and
    [`:picture-in-picture`](:picture-in-picture)
- Complete list of [pseudo-classes](pseudo-classes.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:modal>
