rect()
======

**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.

The `rect()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
function creates a rectangle at the specified distance from the top and
left edges of the containing block. It is a basic shape function of the
[`<basic-shape>`](basic-shape.md) [data type](css_types.md). You can use
the `rect()` function in CSS properties such as
[`offset-path`](offset-path.md) to create the rectangular path along
which an element moves and in [`clip-path`](clip-path.md) to define the
shape of the clipping region.

Syntax
------

[css]

```
offset-path: rect(0 1% auto 3% round 0 1px);
clip-path: rect(50px 70px 80% 20%);
```

### Values

```css
starting with the top edge offset and going clockwise, and an optional
`round` keyword with the `border-radius` parameter to add rounded
corners to the rectangle. Each offset value can be either a `<length>`,
a `<percentage>`, or the keyword `auto`.

[`<length-percentage>`](#length-percentage)

:   Specifies the [`<length-percentage>`](../length-percentage) value of
    the distance of the top, right, bottom, or left edge of the
    rectangle from the top or left edge of the containing block. The
    first (top) and third (bottom) values are distances from the top
    edge of the containing block, and the second (right) and fourth
    (left) values are distances from the left edge of the containing
    block. The second (right) and third (bottom) values are clamped by
    the fourth (left) and second (top) values, respectively, to prevent
    the bottom edge from crossing over the top edge and right edge from
    crossing over the left edge. For example, `rect(10px 0 0 20px)` is
    clamped to `rect(10px 20px 10px 20px)`.

[`auto`](#auto)

:   Makes the edge for which this value is used to coincide with the
    corresponding edge of the containing block. If `auto` is used for
    the first (top) or fourth (left) value, the value of `auto` is `0`,
    and if used for the second (right) or third (bottom) value, the
    value of `auto` is `100%`.

[`round <'border-radius'>`](#round_border-radius)

:   Specifies the radius of the rounded corners of the rectangle using
    the same syntax as the CSS [`border-radius`](../border-radius)
    shorthand property. This parameter is optional.

Examples
--------

### Creating offset-path using rect() 

In this example, the [`offset-path`](../offset-path) property uses the
`rect()` function to define the shape of the path on which the element,
a red box in this case, moves. Three different scenarios are shown, each
using different values for the `rect()` function. The arrow inside the
boxes points to the right edge of the box.

[html]

```html
<div class="container">
  Rectangular path 1
  <div class="path rect-path-1">→</div>
</div>
<div class="container">
  Rectangular path 2
  <div class="path rect-path-2">→</div>
</div>
<div class="container">
  Rectangular path 3
  <div class="path rect-path-3">→</div>
</div>
```

[css]

```
.container {
  position: relative;
  display: inline-block;
  width: 200px;
  height: 200px;
  border: 1px solid black;
  margin: 15px;
  text-align: center;
}

.path {
  width: 40px;
  height: 40px;
  background-color: red;
  position: absolute;
  animation: move 10s linear infinite;
}

.rect-path-1 {
  offset-path: rect(50px 150px 200px 50px round 20%);
```css

.rect-path-2 {
  offset-path: rect(50px auto 200px 50px round 20%);
}

.rect-path-3 {
  offset-path: rect(50px auto 200px auto);
}

@keyframes move {
  0% {
    offset-distance: 0%;
  }
  100% {
    offset-distance: 100%;
  }
}
```

#### Result

- The path 1 rectangle specifies the distances of the four edges (top,
    right, bottom, and left) from the containing block. The top and
    bottom values are distances from the top edge of the containing
    block. The right and left values are distances from the left edge of
    the containing block. In addition, the corner of the rectangle is
    rounded at `20%`, making the red box element follow the rounded
    corners as it moves along this path. Notice how the arrow inside the
    box follows curve at the rectangular path corners.
- The path 2 rectangle is similar to the path 1 rectangle, except that
    the right value is `auto`, which is equal to the value `100%`. This
    causes the right edge of the rectangle to match the right edge of
    the containing block, creating a wider rectangle than path 1.
- The path 3 rectangle specifies both the left and right edge
    parameters as `auto` and omits the `round <'border-radius'>`
    parameter. This creates a rectangle that has the width of the
    containing block and rectangular corners instead of rounded corners
    like in path 1 and path 2 rectangles. Notice the movement of the
    arrow inside this box at the corners.

Specifications
--------------

  -----------------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------------

  [CSS Shapes Module Level 1\
  [\#
  funcdef-basic-shape-rect]](https://drafts.csswg.org/css-shapes-1/#funcdef-basic-shape-rect)

  -----------------------------------------------------------------------------------------------------

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

`rect`

116Only supported on the `offset-path` property.

116Only supported on the `offset-path` property.

117

No

102Only supported on the `offset-path` property.

No

116Only supported on the `offset-path` property.

116Only supported on the `offset-path` property.

No

NoOnly supported on the `offset-path` property.

No

NoOnly supported on the `offset-path` property.

See also
--------

- [`inset()`](basic-shape.md#inset) function
- [`xywh()`](basic-shape.md#xywh) function
- [`clip-path`](clip-path.md) property
- [`offset-path`](offset-path.md) property
- [`<basic-shape>`](basic-shape.md) data type
- [CSS shapes](css_shapes.md) module
- [Guide to basic shapes](basic_shapes.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/basic-shape/rect>
