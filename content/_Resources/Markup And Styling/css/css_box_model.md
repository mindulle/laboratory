CSS box model
=============

The **CSS box model** module defines the rectangular boxes, including
their padding and margin, that are generated for elements and laid out
according to the [visual formatting model](visual_formatting_model.md).

Box model overview
------------------

A box in CSS consists of a content area, which is where any text,
images, or other HTML elements are displayed. This is optionally
surrounded by padding, a border, and a margin, on one or more sides. The
box model describes how these elements work together to create a box as
displayed by CSS. To learn more about it read [](introduction_to_the_css_box_model.md).

### Box-edge keywords

The Box Model specification defines a set of keywords that refer to the
edges of each part of the box, these are used as keyword values in CSS
including as a value for the [`box-sizing`](box-sizing.md) property, to
control how the box model calculates its size.

[`content-box`](#content-box)

:   The edge of the content area of the box.

[`padding-box`](#padding-box)

:   The edge of the padding of the box, if there is no padding on a side
    then this is the same as `content-box`.

[`border-box`](#border-box)

:   The edge of the border of the box, if there is no border on a side
    then this is the same as `padding-box`.

[`margin-box`](#margin-box)

:   The edge of the margin of the box, if there is no margin on a side
    then this is the same as `border-box`.

[`stroke-box`](#stroke-box)

:   In SVG refers to the stroke bounding box, in CSS treated as
    `content-box`.

[`view-box`](#view-box)

:   In SVG refers to the nearest SVG viewport element\'s origin box,
    which is a rectangle with the width and height of the initial SVG
    user coordinate system established by the `viewBox` attribute for
    that element. In CSS treated as `border-box`.

Reference
---------

**Note:** This specification defines the physical padding and margin
properties. Flow-relative properties, which relate to text direction,
are defined in [](css_logical_properties_and_values.md).

### Properties for controlling the margin of a box

Margins surround the border edge of a box, and provide spacing between
boxes.

- [`margin`](margin.md)
- [`margin-bottom`](margin-bottom.md)
- [`margin-left`](margin-left.md)
- [`margin-right`](margin-right.md)
- [`margin-top`](margin-top.md)
- [`margin-trim`](margin-trim.md) [Experimental]

### Properties for controlling the padding for a box

Padding is inserted between the content edge and border edge of a box.

- [`padding`](padding.md)
- [`padding-bottom`](padding-bottom.md)
- [`padding-left`](padding-left.md)
- [`padding-right`](padding-right.md)
- [`padding-top`](padding-top.md)

### Other properties

There are other properties that relate to the box model, that are
defined elsewhere.

[Borders](css_backgrounds_and_borders.md)

:   The border properties specify the thickness of the border, drawing
    style and color.

[Overflow](overflow.md)

:   Controls what happens when there is too much content to fit into a
    box.

Guides
------

[Introduction to the CSS box model](introduction_to_the_css_box_model.md)

:   Explains one of the fundamental concept of CSS: the box model. This
    model defines how CSS lays out elements, including their content,
    padding, border, and margin areas.

[Mastering margin collapsing](mastering_margin_collapsing.md)

:   Sometimes, two adjacent margins are collapsed into one. This article
    describes the rules that govern when and why this happens, and how
    to control it.

[Visual formatting model](visual_formatting_model.md)

:   Explains the visual formatting model.

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Box Model Module Level 3\
  ](https://drafts.csswg.org/css-box/)

  -----------------------------------------------------------------------

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model>
