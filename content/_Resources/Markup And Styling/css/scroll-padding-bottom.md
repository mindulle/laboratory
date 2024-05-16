scroll-padding-bottom
=====================

The `scroll-padding-bottom` property defines offsets for the bottom of
the *optimal viewing region* of the scrollport: the region used as the
target region for placing things in view of the user. This allows the
author to exclude regions of the scrollport that are obscured by other
content (such as fixed-positioned toolbars or sidebars) or to put more
breathing room between a targeted element and the edges of the
scrollport.

Try it
------

Syntax
------

[css]

```css
/* Keyword values */
scroll-padding-bottom: auto;

/* <length> values */
scroll-padding-bottom: 10px;
scroll-padding-bottom: 1em;
scroll-padding-bottom: 10%;

/* Global values */
scroll-padding-bottom: inherit;
scroll-padding-bottom: initial;
scroll-padding-bottom: revert;
scroll-padding-bottom: revert-layer;
scroll-padding-bottom: unset;
```

### Values

[`<length-percentage>`](#length-percentage)

:   An inwards offset from the bottom edge of the scrollport, as a valid
    length or a percentage.

[`auto`](#auto)

:   The offset is determined by the user agent. This will generally be
    0px, but a user agent is able to detect and do something else if a
    non-zero value is more appropriate.

Formal definition
-----------------

  ---------------------------------- ------------------------------------------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         scroll containers
  [Inherited](inheritance.md)           no
  Percentages                        relative to the scroll container\'s scrollport
  [Computed value](computed_value.md)   as specified
  Animation type                     by computed value type
  ---------------------------------- ------------------------------------------------

Formal syntax
-------------

```
scroll-padding-bottom = 
  auto                       |
  <length-percentage [0,∞]>  

<length-percentage> = 
  <length>      |
  <percentage>  
```

Specifications
--------------

  ------------------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------------------

  [CSS Scroll Snap Module Level 1\
  [\#
  padding-longhands-physical]](https://drafts.csswg.org/css-scroll-snap/#padding-longhands-physical)

  ------------------------------------------------------------------------------------------------------------

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

`scroll-padding-bottom`

69

79

68

No

56

14.1

11--14.1Scroll padding is not applied for scrolls to fragment target or
`scrollIntoView()`, see [bug 179379](https://webkit.org/b/179379).

69

69

68

48

14.5

11--14.5Scroll padding is not applied for scrolls to fragment target or
`scrollIntoView()`, see [bug 179379](https://webkit.org/b/179379).

10.0

See also
--------

- [CSS scroll snap](css_scroll_snap.md)
- [Well-controlled scrolling with CSS scroll
    snap](https://web.dev/css-scroll-snap/)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-padding-bottom>
