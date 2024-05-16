hover
=====

The `hover` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[media feature](@media.md#media_features) can be used to test whether
the user\'s *primary* input mechanism can hover over elements.

Syntax
------

The `hover` feature is specified as a keyword value chosen from the list
below.

[`none`](#none)

:   The primary input mechanism cannot hover at all or cannot
    conveniently hover (e.g., many mobile devices emulate hovering when
    the user performs an inconvenient long tap), or there is no primary
    pointing input mechanism.

[`hover`](#hover)

:   The primary input mechanism can conveniently hover over elements.

Examples
--------

### HTML

[html]

```html
<a href="#">Try hovering over me!</a>
```

### CSS

[css]

```css
/* default hover effect */
a:hover {
  color: black;
  background: yellow;
}

@media (hover: hover) {
  /* when hover is supported */
  a:hover {
    color: white;
    background: black;
  }
}
```

### Result

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [Media Queries Level 4\
  [\# hover]](https://drafts.csswg.org/mediaqueries/#hover)

  -----------------------------------------------------------------------

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

`hover`

38Before Chrome 41, the implementation was buggy and reported
`(hover: none)` on non-touch-based computers with a mouse/trackpad. See
[bug 441613](https://crbug.com/441613).

12

64

No

28

9

38Before Chrome 41, the implementation was buggy and reported
`(hover: none)` on non-touch-based computers with a mouse/trackpad. See
[bug 441613](https://crbug.com/441613).

50

64

28

9

5.0

See also
--------

- [Using Media Queries](using_media_queries.md)
- [\@media](@media.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@media/hover>
