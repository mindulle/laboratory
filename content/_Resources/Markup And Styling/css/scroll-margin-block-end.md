scroll-margin-block-end
=======================

The `scroll-margin-block-end` property defines the margin of the scroll
snap area at the end of the block dimension that is used for snapping
this box to the snapport. The scroll snap area is determined by taking
the transformed border box, finding its rectangular bounding box
(axis-aligned in the scroll container\'s coordinate space), then adding
the specified outsets.

Try it
------

Syntax
------

[css]

```css
/* <length> values */
scroll-margin-block-end: 10px;
scroll-margin-block-end: 1em;

/* Global values */
scroll-margin-block-end: inherit;
scroll-margin-block-end: initial;
scroll-margin-block-end: revert;
scroll-margin-block-end: revert-layer;
scroll-margin-block-end: unset;
```

### Values

[`<length>`](length.md)

:   An outset from the block end edge of the scroll container.

Formal definition
-----------------

  ---------------------------------- ------------------------
  [Initial value](initial_value.md)     `0`
  Applies to                         all elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     by computed value type
  ---------------------------------- ------------------------

Formal syntax
-------------

```
scroll-margin-block-end = 
  <length>  
```

Specifications
--------------

  --------------------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------------------

  [CSS Scroll Snap Module Level 1\
  [\#
  margin-longhands-logical]](https://drafts.csswg.org/css-scroll-snap/#margin-longhands-logical)

  --------------------------------------------------------------------------------------------------------

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

`scroll-margin-block-end`

69

79

68

No

56

15

69

69

68

48

15

10.0

See also
--------

- [CSS scroll snap](css_scroll_snap.md)
- [Well-controlled scrolling with CSS scroll
    snap](https://web.dev/css-scroll-snap/)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-margin-block-end>
