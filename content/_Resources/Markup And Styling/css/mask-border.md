mask-border
===========

The `mask-border`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [](shorthand_properties.md) lets you create a mask along the edge of
an element\'s border.

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`mask-border-mode`](mask-border-mode.md)
- [`mask-border-outset`](mask-border-outset.md)
- [`mask-border-repeat`](mask-border-repeat.md)
- [`mask-border-slice`](mask-border-slice.md)
- [`mask-border-source`](mask-border-source.md)
- [`mask-border-width`](mask-border-width.md)

Syntax
------

[css]

```css
/* source | slice */
mask-border: url("border-mask.png") 25;

/* source | slice | repeat */
mask-border: url("border-mask.png") 25 space;

/* source | slice | width */
mask-border: url("border-mask.png") 25 / 35px;

/* source | slice | width | outset | repeat | mode */
mask-border: url("border-mask.png") 25 / 35px / 12px space alpha;

/* Global values */
mask-border: inherit;
mask-border: initial;
mask-border: revert;
mask-border: revert-layer;
mask-border: unset;
```

### Values

[`<'mask-border-source'>`](#mask-border-source)

:   The source image. See [`mask-border-source`](mask-border-source.md).

[`<'mask-border-slice'>`](#mask-border-slice)

:   The dimensions for slicing the source image into regions. Up to four
    values may be specified. See
    [`mask-border-slice`](mask-border-slice.md).

[`<'mask-border-width'>`](#mask-border-width)

:   The width of the border mask. Up to four values may be specified.
    See [`mask-border-width`](mask-border-width.md).

[`<'mask-border-outset'>`](#mask-border-outset)

:   The distance of the border mask from the element\'s outside edge. Up
    to four values may be specified. See
    [`mask-border-outset`](mask-border-outset.md).

[`<'mask-border-repeat'>`](#mask-border-repeat)

:   Defines how the edge regions of the source image are adjusted to fit
    the dimensions of the border mask. Up to two values may be
    specified. See [`mask-border-repeat`](mask-border-repeat.md).

[`<'mask-border-mode'>`](#mask-border-mode)

:   Defines whether the source image is treated as a luminance mask or
    alpha mask. See [`mask-border-mode`](mask-border-mode.md).

Formal definition
-----------------

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md)    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](mask-border-mode.md): |
|                                   |     `alpha`                       |
|                                   | -   [](mask-border-outset.md): |
|                                   |     `0`                           |
|                                   | -   [](mask-border-repeat.md): |
|                                   |     `stretch`                     |
|                                   | -   [](mask-border-slice.md): |
|                                   |     `0`                           |
|                                   | -   [](mask-border-source.md): |
|                                   |     `none`                        |
|                                   | -   [](mask-border-width.md): |
|                                   |     `auto`                        |
+-----------------------------------+-----------------------------------+
| Applies to                        | all elements; In SVG, it applies  |
|                                   | to container elements excluding   |
|                                   | the                               |
|                                   | [`<defs                           |
|                                   | >`](https://developer.mozilla.org |
|                                   | /en-US/docs/Web/SVG/Element/defs) |
|                                   | element and all graphics elements |
+-----------------------------------+-----------------------------------+
| [Inherited](inheritance.md)          | no                                |
+-----------------------------------+-----------------------------------+
| Percentages                       | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](mask-border-slice.md): |
|                                   |     refer to size of the mask     |
|                                   |     border image                  |
|                                   | -   [](mask-border-width.md): |
|                                   |     relative to width/height of   |
|                                   |     the mask border image area    |
+-----------------------------------+-----------------------------------+
| [Computed value](computed_value.md)  | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](mask-border-mode.md): |
|                                   |     as specified                  |
|                                   | -   [](mask-border-outset.md): |
|                                   |     as specified, but with        |
|                                   |     relative lengths converted    |
|                                   |     into absolute lengths         |
|                                   | -   [](mask-border-repeat.md): |
|                                   |     as specified                  |
|                                   | -   [](mask-border-slice.md): |
|                                   |     as specified                  |
|                                   | -   [](mask-border-source.md): |
|                                   |     as specified, but with        |
|                                   |     [`url()`](url.md) values made    |
|                                   |     absolute                      |
|                                   | -   [](mask-border-width.md): |
|                                   |     as specified, but with        |
|                                   |     relative lengths converted    |
|                                   |     into absolute lengths         |
+-----------------------------------+-----------------------------------+
| Animation type                    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](mask-border-mode.md): |
|                                   |     discrete                      |
|                                   | -   [](mask-border-outset.md): |
|                                   |     discrete                      |
|                                   | -   [](mask-border-repeat.md): |
|                                   |     discrete                      |
|                                   | -   [](mask-border-slice.md): |
|                                   |     discrete                      |
|                                   | -   [](mask-border-source.md): |
|                                   |     discrete                      |
|                                   | -   [](mask-border-width.md): |
|                                   |     discrete                      |
+-----------------------------------+-----------------------------------+
| Creates [stacking                 | yes                               |
| cont                              |                                   |
| ext](css_positioned_layout/unders |                                   |
| tanding_z-index/stacking_context) |                                   |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
mask-border = 
  <'mask-border-source'>                              ||
  <'mask-border-slice'> [ / <'mask-border-width'>? [ / <'mask-border-outset'> ]? ]?  ||
  <'mask-border-repeat'>                              ||
  <'mask-border-mode'>                                
```

Examples
--------

### Setting a bitmap-based mask border

In this example, we will mask an element\'s border with a diamond
pattern. The source for the mask is a \".png\" file of 90 by 90 pixels,
with three diamonds going vertically and horizontally:

To match the size of a single diamond, we will use a value of 90 divided
by 3, or `30`, for slicing the image into corner and edge regions. A
repeat value of `round` will make the mask slices fit evenly, i.e.,
without clipping or gaps.

Specifications
--------------

  ---------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------

  [CSS Masking Module Level 1\
  [\#
  the-mask-border]](https://drafts.fxtf.org/css-masking/#the-mask-border)

  ---------------------------------------------------------------------------------

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

`mask-border`

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

- [`mask-border-mode`](mask-border-mode.md)
- [`mask-border-outset`](mask-border-outset.md)
- [`mask-border-repeat`](mask-border-repeat.md)
- [`mask-border-source`](mask-border-source.md)
- [`mask-border-width`](mask-border-width.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/mask-border>
