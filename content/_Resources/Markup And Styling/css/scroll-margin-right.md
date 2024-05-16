scroll-margin-right
===================

The `scroll-margin-right` property defines the right margin of the
scroll snap area that is used for snapping this box to the snapport. The
scroll snap area is determined by taking the transformed border box,
finding its rectangular bounding box (axis-aligned in the scroll
container\'s coordinate space), then adding the specified outsets.

Try it
------

Syntax
------

[css]

```css
/* <length> values */
scroll-margin-right: 10px;
scroll-margin-right: 1em;

/* Global values */
scroll-margin-right: inherit;
scroll-margin-right: initial;
scroll-margin-right: revert;
scroll-margin-right: revert-layer;
scroll-margin-right: unset;
```

### Values

[`<length>`](length.md)

:   An outset from the right edge of the scroll container.

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
scroll-margin-right = 
  <length>  
```

Specifications
--------------

  ----------------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------------

  [CSS Scroll Snap Module Level 1\
  [\#
  margin-longhands-physical]](https://drafts.csswg.org/css-scroll-snap/#margin-longhands-physical)

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

`scroll-margin-right`

69

79

68

No

56

14.1

11Before version 14.1, scroll margin is not applied for scrolls to
fragment target or `scrollIntoView()`, see [bug
189265](https://webkit.org/b/189265).

69

69

68

48

14.5

11Before version 14.5, scroll margin is not applied for scrolls to
fragment target or `scrollIntoView()`, see [bug
189265](https://webkit.org/b/189265).

10.0

See also
--------

- [CSS scroll snap](css_scroll_snap.md)
- [Well-controlled scrolling with CSS scroll
    snap](https://web.dev/css-scroll-snap/)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-margin-right>
