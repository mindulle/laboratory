:paused
=======

The `:paused` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) selector represents an element that is
playable, such as
[`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio)
or
[`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video),
when that element is \"paused\" (i.e. not \"playing\").

A resource is paused if the user explicitly paused it, or if it is in a
non-activated or other non-playing state, like \"loaded, hasn\'t been
activated yet\". This is different from `:buffering` or `:stalled`,
which are states that occur while the resource is considered
\"playing\".

Syntax
------

[css]

```css
:paused {
  /* ... */
}
```

Examples
--------

### CSS

[css]

```css
:paused {
  border: 5px solid orange;
}
```

Specifications
--------------

  --------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------

  [Selectors Level 4\
  [\#
  selectordef-paused]](https://drafts.csswg.org/selectors/#selectordef-paused)

  --------------------------------------------------------------------------------------

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

`:paused`

No

No

No

No

No

15.4

No

No

No

No

15.4

No

See also
--------

- [`:buffering`](:buffering)
- [`:muted`](:muted)
- [`:playing`](:playing)
- [`:seeking`](:seeking)
- [`:stalled`](:stalled)
- [`:volume-locked`](:volume-locked)
- [CSS selectors](css_selectors.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:paused>
