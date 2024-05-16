mask-border-width
=================

The `mask-border-width`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the width of an element\'s [mask border](mask-border.md).

Syntax
------

[css]

```css
/* Keyword value */
mask-border-width: auto;

/* <length> value */
mask-border-width: 1rem;

/* <percentage> value */
mask-border-width: 25%;

/* <number> value */
mask-border-width: 3;

/* top and bottom | left and right */
mask-border-width: 2em 3em;

/* top | left and right | bottom */
mask-border-width: 5% 15% 10%;

/* top | right | bottom | left */
mask-border-width: 5% 2em 10% auto;

/* Global values */
mask-border-width: inherit;
mask-border-width: initial;
mask-border-width: revert;
mask-border-width: revert-layer;
mask-border-width: unset;
```

The `mask-border-width` property may be specified using one, two, three,
or four values chosen from the list of values below.

- When **one** value is specified, it applies the same width to **all
    four sides**.
- When **two** values are specified, the first width applies to the
    **top and bottom**, the second to the **left and right**.
- When **three** values are specified, the first width applies to the
    **top**, the second to the **left and right**, the third to the
    **bottom**.
- When **four** values are specified, the widths apply to the **top**,
    **right**, **bottom**, and **left** in that order (clockwise).

### Values

[`<length-percentage>`](#length-percentage)

:   The width of the mask border, specified as a [`<length>`](length.md) or
    a [`<percentage>`](percentage.md). Percentages are relative to the
    *width* of the border area for horizontal offsets and the *height*
    of the border area for vertical offsets. Must not be negative.

[`<number>`](#number)

:   The width of the mask border, specified as a multiple of the
    corresponding [`border-width`](border-width.md). Must not be negative.

[`auto`](#auto)

:   The width of the mask border is made equal to the intrinsic width or
    height (whichever is applicable) of the corresponding
    [`mask-border-slice`](mask-border-slice.md). If the image does not have
    the required intrinsic dimension, the corresponding `border-width`
    is used instead.

Formal definition
-----------------

  ---------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         all elements; In SVG, it applies to container elements excluding the [`<defs>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/defs) element and all graphics elements
  [Inherited](inheritance.md)           no
  Percentages                        relative to width/height of the mask border image area
  [Computed value](computed_value.md)   as specified, but with relative lengths converted into absolute lengths
  Animation type                     discrete
  ---------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
mask-border-width = 
  [ <length-percentage> | <number> | auto ]  

<length-percentage> = 
  <length>      |
  <percentage>  
```

Examples
--------

### Basic usage

This property doesn\'t appear to be supported anywhere yet. When it
eventually starts to be supported, it will serve to define the width of
the border mask --- setting this to a different value to
[`mask-border-slice`](mask-border-slice.md) will cause the slices to be
scaled to fit the border mask.

[css]

```css
mask-border-width: 30 fill;
```

Chromium-based browsers support an outdated version of this property ---
`mask-box-image-width` --- with a prefix:

[css]

```css
-webkit-mask-box-image-width: 20px;
```

**Note:** The [`mask-border`](mask-border.md) page features a working
example (using the out-of-date prefixed border mask properties supported
in Chromium), so you can get an idea of the effect.

Specifications
--------------

  ---------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------

  [CSS Masking Module Level 1\
  [\#
  the-mask-border-width]](https://drafts.fxtf.org/css-masking/#the-mask-border-width)

  ---------------------------------------------------------------------------------------------

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

`mask-border-width`

1

79

No

No

15

3.1

4.4

18

No

14

3

1.0

See also
--------

- [`mask-border`](mask-border.md)
- [`mask-border-mode`](mask-border-mode.md)
- [`mask-border-outset`](mask-border-outset.md)
- [`mask-border-repeat`](mask-border-repeat.md)
- [`mask-border-source`](mask-border-source.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/mask-border-width>
