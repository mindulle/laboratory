\<box-edge\>
============

The `<box-edge>` value types represent a [](introduction_to_the_css_box_model.md) keyword, such as
[`content-box`](#content-box) and [`border-box`](#border-box). The
box-edge keywords are used to define different aspects of an element\'s
box model and how elements are positioned and rendered on screen.

The box-edge keywords are the components of, but not limited to, the
data types `<visual-box>`, `<layout-box>`, `<paint-box>`, `<coord-box>`,
and `<geometry-box>`. These types are applied to properties such as
[`transform-box`](transform-box.md) and
[`background-clip`](background-clip.md).

Syntax
------

```
<visual-box> = content-box | padding-box | border-box /* the three <box> values */
<layout-box> = <box> | margin-box /* the <shape-box> values */
<paint-box> = <box> | fill-box | stroke-box
<coord-box> = <box> | fill-box | stroke-box | view-box
<geometry-box> = <shape-box> | fill-box | stroke-box | view-box
```

### Values

A `<box-edge>` can be of the type `<visual-box>`, `<layout-box>`,
`<paint-box>`, `<coord-box>`, or `<geometry-box>`.

[`<visual-box>`](#visual-box)

:   Refers to the rectangular box generated for an element as seen by a
    user on a web page. It includes the element\'s content, padding, and
    border. Also referred to as `<box>`, this value excludes the margin
    area. This value type is used for the
    [`background-clip`](background-clip.md) and
    [`overflow-clip-margin`](overflow-clip-margin.md) properties.

[`<layout-box>`](#layout-box)

:   Refers to the space occupied by an element, including its content,
    padding, border, and margin. This value type is used for layout and
    positioning purposes. Also referred to as `<shape-box>`, this value
    type is used for the [`shape-outside`](shape-outside.md) property.

[`<paint-box>`](#paint-box)

:   Refers to the area within the layout box that is used to visually
    render the content. This includes the area where the element\'s
    background and borders are painted. As an element\'s paintable area
    does not include its margins, this value excludes `margin-box`.

[`<coord-box>`](#coord-box)

:   Refers to the coordinate box used for positioning and sizing an
    element within its parent container. It is used to control how
    content flows around the edges of the box. It excludes the margin
    area. This value type is used for the [`offset-path`](offset-path.md)
    property.

[`<geometry-box>`](#geometry-box)

:   Defines the reference box for a [basic shape](basic-shape.md), or if
    specified by itself, causes the edges of the specified box,
    including any corner shaping (such as a
    [`border-radius`](border-radius.md)), to be the clipping path. This
    value type is used for the [`clip-path`](clip-path.md),
    [`mask-clip`](mask-clip.md), and [`mask-origin`](mask-origin.md)
    properties and the SVG `clip-path` attribute.

### Keywords

The `<box-edge>` keywords are defined as follows:

[`content-box`](#content-box)

:   Refers to the outer edge of the box\'s content area. . The content
    box is the innermost box. The content area contains the actual
    content, such as text, images, or other HTML elements. In SVG, this
    value is treated as `fill-box`.

[`padding-box`](#padding-box)

:   Refers to the outer edge of the padding of the box. If there is no
    padding on a side, then the value is the same as `content-box`. In
    SVG, `padding-box` is treated as `fill-box`. The padding area
    surrounds the content area, starting at the outer edge of the
    content box.

[`border-box`](#border-box)

:   Refers to the outer edge of the border of the box. If there is no
    border on a side, then the value is the same as `padding-box`. In
    SVG, `border-box` is treated as `stroke-box`. The border area
    surrounds the padding area, starting at the outer edge of the
    padding box.

[`margin-box`](#margin-box)

:   Refers to the outer edge of the margin of the box. If there is no
    margin on a side, then the value is the same as `border-box`. In
    SVG, `margin-box` is treated as `stroke-box`.

[`fill-box`](#fill-box)

:   Refers to the object bounding box in SVG. In CSS, `fill-box` is
    treated as `content-box`. It is used to wrap the content around the
    edges defined by the `coord-box` values.

[`stroke-box`](#stroke-box)

:   Refers to the stroke bounding box in SVG. In CSS, `stroke-box` is
    treated as `border-box`. It is used to define the shape of the
    element when strokes are applied.

[`view-box`](#view-box)

:   Refers to the nearest SVG viewport element\'s origin box. The origin
    box is a rectangle with the width and height of the initial SVG user
    coordinate system established by the `viewBox` attribute for that
    element. The origin box is positioned such that its top left corner
    is anchored at the [](coordinate_systems.md) origin. In CSS, `view-box` is
    treated as `border-box`.

    **Note:** When the SVG viewport is not anchored at the origin, the
    origin box does not correspond to the SVG viewport.

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Box Model Module Level 4\
  [\# keywords]](https://drafts.csswg.org/css-box-4/#keywords)

  -----------------------------------------------------------------------

See also
--------

- [CSS box model](css_box_model.md) module

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/box-edge>
