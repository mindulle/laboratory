scroll-snap-align
=================

The `scroll-snap-align` property specifies the box\'s snap position as
an alignment of its snap area (as the alignment subject) within its snap
container\'s snapport (as the alignment container). The two values
specify the snapping alignment in the block axis and inline axis,
respectively. If only one value is specified, the second value defaults
to the same value.

Try it
------

Syntax
------

[css]

```css
/* Keyword values */
scroll-snap-align: none;
scroll-snap-align: start end; /* when two values set first is block, second inline */
scroll-snap-align: center;

/* Global values */
scroll-snap-align: inherit;
scroll-snap-align: initial;
scroll-snap-align: revert;
scroll-snap-align: revert-layer;
scroll-snap-align: unset;
```

### Values

[`none`](#none)

:   The box does not define a snap position in that axis.

[`start`](#start)

:   The start alignment of this box\'s scroll snap area, within the
    scroll container\'s snapport is a snap position in this axis.

[`end`](#end)

:   The end alignment of this box\'s scroll snap area, within the scroll
    container\'s snapport is a snap position in this axis.

[`center`](#center)

:   The center alignment of this box\'s scroll snap area, within the
    scroll container\'s snapport is a snap position in this axis.

Formal definition
-----------------

  ---------------------------------- --------------
  [Initial value](initial_value.md)     `none`
  Applies to                         all elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- --------------

Formal syntax
-------------

```
scroll-snap-align = 
  [ none | start | end | center ]  
```

Specifications
--------------

  ------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------

  [CSS Scroll Snap Module Level 1\
  [\#
  scroll-snap-align]](https://drafts.csswg.org/css-scroll-snap/#scroll-snap-align)

  ------------------------------------------------------------------------------------------

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

`scroll-snap-align`

69

79

68

No

56

11

69

69

68

48

11

10.0

See also
--------

- [CSS scroll snap](css_scroll_snap.md)
- [Well-controlled scrolling with CSS scroll
    snap](https://web.dev/css-scroll-snap/)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-snap-align>
