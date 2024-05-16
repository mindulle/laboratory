border-image-width
==================

Baseline: [Widely supported]
---------------------------------------

Baseline is determined by this web feature being supported on the
current and the previous major versions of major browsers.

- [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-unified-view-stable-web-features/)
- [See full compatibility](#browser_compatibility)

The `border-image-width`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the width of an element\'s [border image](border-image.md).

Try it
------

If this property\'s value is greater than the element\'s
[`border-width`](border-width.md), the border image will extend beyond the
padding (and/or content) edge.

Syntax
------

[css]

```css
/* Keyword value */
border-image-width: auto;

/* <length> value */
border-image-width: 1rem;

/* <percentage> value */
border-image-width: 25%;

/* <number> value */
border-image-width: 3;

/* top and bottom | left and right */
border-image-width: 2em 3em;

/* top | left and right | bottom */
border-image-width: 5% 15% 10%;

/* top | right | bottom | left */
border-image-width: 5% 2em 10% auto;

/* Global values */
border-image-width: inherit;
border-image-width: initial;
border-image-width: revert;
border-image-width: revert-layer;
border-image-width: unset;
```

The `border-image-width` property may be specified using one, two,
three, or four values chosen from the list of values below.

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

:   The width of the border, specified as a [`<length>`](length.md) or a
    [`<percentage>`](percentage.md). Percentages are relative to the
    *width* of the border image area for horizontal offsets and the
    *height* of the border image area for vertical offsets. Must not be
    negative.

[`<number>`](#number)

:   The width of the border, specified as a multiple of the
    corresponding [`border-width`](border-width.md). Must not be negative.

[`auto`](#auto)

:   The width of the border is made equal to the intrinsic width or
    height (whichever is applicable) of the corresponding
    [`border-image-slice`](border-image-slice.md). If the image does not
    have the required intrinsic dimension, the corresponding
    `border-width` is used instead.

Formal definition
-----------------

  ---------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `1`
  Applies to                         all elements, except internal table elements when [`border-collapse`](border-collapse.md) is `collapse`. It also applies to [`::first-letter`](::first-letter).
  [Inherited](inheritance.md)           no
  Percentages                        refer to the width or height of the border image area
  [Computed value](computed_value.md)   as specified, but with relative lengths converted into absolute lengths
  Animation type                     by computed value type
  ---------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
border-image-width = 
  [ <length-percentage [0,∞]> | <number [0,∞]> | auto ]  

<length-percentage> = 
  <length>      |
  <percentage>  
```

Examples
--------

### Tiling a border image

This example creates a border image using the following \".png\" file,
which is 90 by 90 pixels:

Thus, each circle in the source image is 30 by 30 pixels.

#### HTML

[html]

```html
<p>
  Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy
  eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam
  voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita
  kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.
</p>
```

#### CSS

[css]

```css
p {
  border: 20px solid;
  border-image: url("border.png") 30 round;
  border-image-width: 16px;
  padding: 40px;
}
```

#### Result

Specifications
--------------

  ----------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------

  [CSS Backgrounds and Borders Module Level 3\
  [\#
  the-border-image-width]](https://drafts.csswg.org/css-backgrounds/#the-border-image-width)

  ----------------------------------------------------------------------------------------------------

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

`border-image-width`

15Before Chrome 112, a border image\'s absolute or percentage length
width may not take precedence over a narrower `border-width` ([bug
767352](https://crbug.com/767352)).

12Before Edge 112, a border image\'s absolute or percentage length width
may not take precedence over a narrower `border-width` ([bug
767352](https://crbug.com/767352)).

13

11

15Before Opera 98, a border image\'s absolute or percentage length width
may not take precedence over a narrower `border-width` ([bug
767352](https://crbug.com/767352)).

6

4.4Before Chrome 112, a border image\'s absolute or percentage length
width may not take precedence over a narrower `border-width` ([bug
767352](https://crbug.com/767352)).

18Before Chrome 112, a border image\'s absolute or percentage length
width may not take precedence over a narrower `border-width` ([bug
767352](https://crbug.com/767352)).

14

14Before Opera false, a border image\'s absolute or percentage length
width may not take precedence over a narrower `border-width` ([bug
767352](https://crbug.com/767352)).

6

1.0Before Samsung Internet false, a border image\'s absolute or
percentage length width may not take precedence over a narrower
`border-width` ([bug 767352](https://crbug.com/767352)).

See also
--------

- [Backgrounds and borders](css_backgrounds_and_borders.md)
- [Learn CSS: Backgrounds and
    borders](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Backgrounds_and_borders)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-width>
