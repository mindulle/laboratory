overscroll-behavior-y
=====================

The `overscroll-behavior-y` CSS property sets the browser\'s behavior
when the vertical boundary of a scrolling area is reached.

See [`overscroll-behavior`](overscroll-behavior.md) for a full explanation.

Syntax
------

[css]

```css
/* Keyword values */
overscroll-behavior-y: auto; /* default */
overscroll-behavior-y: contain;
overscroll-behavior-y: none;

/* Global values */
overscroll-behavior-y: inherit;
overscroll-behavior-y: initial;
overscroll-behavior-y: revert;
overscroll-behavior-y: revert-layer;
overscroll-behavior-y: unset;
```

The `overscroll-behavior-y` property is specified as a keyword chosen
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
overscroll-behavior-y = 
  contain  |
  none     |
  auto     
```

Examples
--------

### Preventing an underlying element from scrolling vertically

[css]

```css
.messages {
  height: 220px;
  overflow: auto;
  overscroll-behavior-y: contain;
}
```

See [`overscroll-behavior`](overscroll-behavior.md) for a full example and
explanation.

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

`overscroll-behavior-y`

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
    effects](https://developer.chrome.com/blog/overscroll-behavior/#demo)
- The mapped logical properties:
    [`overscroll-behavior-inline`](overscroll-behavior-inline.md),
    [`overscroll-behavior-block`](overscroll-behavior-block.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/overscroll-behavior-y>
