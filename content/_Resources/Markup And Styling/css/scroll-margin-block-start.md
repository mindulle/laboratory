scroll-margin-block-start
=========================

The `scroll-margin-block-start` property defines the margin of the
scroll snap area at the start of the block dimension that is used for
snapping this box to the snapport. The scroll snap area is determined by
taking the transformed border box, finding its rectangular bounding box
(axis-aligned in the scroll container\'s coordinate space), then adding
the specified outsets.

Try it
------

Syntax
------

[css]

```css
/* <length> values */
scroll-margin-block-start: 10px;
scroll-margin-block-start: 1em;

/* Global values */
scroll-margin-block-start: inherit;
scroll-margin-block-start: initial;
scroll-margin-block-start: revert;
scroll-margin-block-start: revert-layer;
scroll-margin-block-start: unset;
```

### Values

[`<length>`](length.md)

:   An outset from the block start edge of the scroll container.

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
scroll-margin-block-start = 
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

`scroll-margin-block-start`

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
https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-margin-block-start>
