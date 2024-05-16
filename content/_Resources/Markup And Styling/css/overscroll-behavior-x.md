overscroll-behavior-x
=====================

The `overscroll-behavior-x` CSS property sets the browser\'s behavior
when the horizontal boundary of a scrolling area is reached.

See [`overscroll-behavior`](overscroll-behavior.md) for a full explanation.

Syntax
------

[css]

```css
/* Keyword values */
overscroll-behavior-x: auto; /* default */
overscroll-behavior-x: contain;
overscroll-behavior-x: none;

/* Global values */
overscroll-behavior-x: inherit;
overscroll-behavior-x: initial;
overscroll-behavior-x: revert;
overscroll-behavior-x: revert-layer;
overscroll-behavior-x: unset;
```

The `overscroll-behavior-x` property is specified as a keyword chosen
from the list of values below.

### Values

[`auto`](#auto)

:   The default scroll overflow behavior occurs as normal.

[`contain`](#contain)

:   Default scroll overflow behavior (e.g., \"bounce\" effects) is
    observed inside the element where this value is set. However, no
    scroll chaining occurs on neighboring scrolling areas; the
    underlying elements will not scroll. The `contain` value disables
    native browser navigation, including the vertical pull-to-refresh
    gesture and horizontal swipe navigation.

[`none`](#none)

:   No scroll chaining occurs to neighboring scrolling areas, and
    default scroll overflow behavior is prevented.

Formal definition
-----------------

  ---------------------------------- --------------------------------------------------------------------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         non-replaced block-level elements and non-replaced inline-block elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- --------------------------------------------------------------------------

Formal syntax
-------------

```
overscroll-behavior-x = 
  contain  |
  none     |
  auto     
```

Examples
--------

### Preventing an underlying element from scrolling horizontally

In our simple [overscroll-behavior-x
example](https://mdn.github.io/css-examples/overscroll-behavior/overscroll-behavior-x)
(see [source
code](https://github.com/mdn/css-examples/blob/main/overscroll-behavior/overscroll-behavior-x.html)
also), we have two block-level boxes, one inside the other. The outer
box has a large [`width`](_Resources/Markup%20And%20Styling/css/width.md) set on it so the page will scroll
horizontally. The inner box has a small width (and [`height`](_Resources/Markup%20And%20Styling/css/height.md))
set on it so it sits comfortably inside the viewport, but its content is
given a large `width` so it will scroll horizontally.

By default, when the inner box is scrolled and a scroll boundary is
reached, the whole page will begin to scroll, which is probably not what
we want. To avoid this, you can set `overscroll-behavior-x: contain` on
the inner box:

[css]

```css
main > div {
  height: 300px;
  width: 500px;
  overflow: auto;
  position: relative;
  top: 100px;
  left: 100px;
  overscroll-behavior-x: contain;
}
```

Specifications
--------------

  -----------------------------------------------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------------------------------------------

  [CSS Overscroll Behavior Module Level 1\
  [\#
  overscroll-behavior-longhands-physical]](https://drafts.csswg.org/css-overscroll/#overscroll-behavior-longhands-physical)

  -----------------------------------------------------------------------------------------------------------------------------------

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

`overscroll-behavior-x`

63

18Currently the `none` value incorrectly behaves as `contain` (allowing
for the elastic bounce effect).

59

No

50

16

63

63

59

46

16

8.0

See also
--------

- [Take control of your scroll: customizing pull-to-refresh and
    overflow
    effects](https://developer.chrome.com/blog/overscroll-behavior/#full-demo)
- The mapped logical properties:
    [`overscroll-behavior-inline`](overscroll-behavior-inline.md),
    [`overscroll-behavior-block`](overscroll-behavior-block.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior-x>
