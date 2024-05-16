mask-border-slice
=================

The `mask-border-slice`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property divides
the image set by [`mask-border-source`](mask-border-source.md) into
regions. These regions are used to form the components of an element\'s
[mask border](mask-border.md).

Syntax
------

[css]

```css
/* All sides */
mask-border-slice: 30%;

/* top and bottom | left and right */
mask-border-slice: 10% 30%;

/* top | left and right | bottom */
mask-border-slice: 30 30% 45;

/* top | right | bottom | left */
mask-border-slice: 7 12 14 5;

/* Using the `fill` keyword */
mask-border-slice: 10% fill 7 12;

/* Global values */
mask-border-slice: inherit;
mask-border-slice: initial;
mask-border-slice: revert;
mask-border-slice: revert-layer;
mask-border-slice: unset;
```

The `mask-border-slice` property may be specified using one to four
`<number-percentage>` values to represent the position of each image
slice. Negative values are invalid; values greater than their
corresponding dimension are clamped to `100%`.

- When **one** position is specified, it creates all four slices at
    the same distance from their respective sides.
- When **two** positions are specified, the first value creates slices
    measured from the **top and bottom**, the second creates slices
    measured from the **left and right**.
- When **three** positions are specified, the first value creates a
    slice measured from the **top**, the second creates slices measured
    from the **left and right**, the third creates a slice measured from
    the **bottom**.
- When **four** positions are specified, they create slices measured
    from the **top**, **right**, **bottom**, and **left** in that order
    (clockwise).

The optional `fill` value, if used, can be placed anywhere in the
declaration.

### Values

[`<number>`](number.md)

:   Represents an edge offset in *pixels* for raster images and
    *coordinates* for vector images. For vector images, the number is
    relative to the element\'s size, not the size of the source image,
    so percentages are generally preferable in these cases.

[`<percentage>`](percentage.md)

:   Represents an edge offset as a percentage of the source image\'s
    size: the width of the image for horizontal offsets, the height for
    vertical offsets.

[`fill`](#fill)

:   Preserves the middle image region. Its width and height are sized to
    match the top and left image regions, respectively.

Description
-----------

The slicing process creates nine regions in total: four corners, four
edges, and a middle region. Four slice lines, set a given distance from
their respective sides, control the size of the regions.

[](mask-border-slice/border-image-slice.png)

The above diagram illustrates the location of each region.

- Zones 1-4 are corner regions. Each one is used a single time to form
    the corners of the final border image.
- Zones 5-8 are edge regions. These are [](mask-border-repeat.md) in the final border image to
    match the dimensions of the element.
- Zone 9 is the middle region. It is discarded by default, but is used
    like a background image if the keyword `fill` is set.

The [`mask-border-repeat`](mask-border-repeat.md),
[`mask-border-width`](mask-border-width.md), and
[`mask-border-outset`](mask-border-outset.md) properties determine how
these regions are used to form the final mask border.

Formal definition
-----------------

  ---------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `0`
  Applies to                         all elements; In SVG, it applies to container elements excluding the [`<defs>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/defs) element and all graphics elements
  [Inherited](inheritance.md)           no
  Percentages                        refer to size of the mask border image
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
mask-border-slice = 
  [ <number> | <percentage> ] fill?  
```

Examples
--------

### Basic usage

This property doesn\'t appear to be supported anywhere yet. When it
eventually starts to be supported, it will serve to define the size of
the slices taken from the source image, and used to create the border
mask.

[css]

```css
mask-border-slice: 30 fill;
```

Chromium-based browsers support an outdated version of this property ---
`mask-box-image-slice` --- with a prefix:

[css]

```css
-webkit-mask-box-image-slice: 30 fill;
```

**Note:** The [`mask-border`](mask-border.md) page features a working
example (using the out-of-date prefixed border mask properties supported
in Chromium), so you can get an idea of the effect.

**Note:** The fill keyword needs to be included if you want the
element\'s content to be visible.

Specifications
--------------

  ---------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------

  [CSS Masking Module Level 1\
  [\#
  the-mask-border-slice]](https://drafts.fxtf.org/css-masking/#the-mask-border-slice)

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

`mask-border-slice`

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
- [`mask-border-width`](mask-border-width.md)
- [](shorthand_properties.md#tricky_edge_cases)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/mask-border-slice>
