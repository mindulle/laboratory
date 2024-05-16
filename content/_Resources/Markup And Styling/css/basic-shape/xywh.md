xywh()
======

**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.

The `xywh()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
function creates a rectangle using the specified distances from the left
(`x`) and top (`y`) edges of the containing block and the specified
width (`w`) and height (`h`) of the rectangle. It is a basic shape
function of the [`<basic-shape>`](basic-shape.md) [](css_types.md). You can use the `xywh()` function in CSS properties
such as [`offset-path`](offset-path.md) to create the rectangular path
along which an element moves and in [`clip-path`](clip-path.md) to
define the shape of the clipping region.

Syntax
------

[css]

```
offset-path: xywh(0 1% 2px 3% round 0 1px 2% 3px);
clip-path: xywh(1px 2% 3px 4em round 0 1% 2px 3em);
```

### Values

```css

:   Specifies the [`<length-percentage>`](../length-percentage) values
    for the `x` and `y` coordinates of the rectangle.

[`<length-percentage [0,∞]>`](#length-percentage_0%E2%88%9E)

:   Specifies non-negative [`<length-percentage>`](../length-percentage)
    values for the width and height of the rectangle. The minimum value
    can be zero, and the maximum value has no limit.

[`round <'border-radius'>`](#round_border-radius)

:   Specifies the radius of the rounded corners of the rectangle using
    the same syntax as the CSS [`border-radius`](../border-radius)
    shorthand property. This parameter is optional.

Examples
--------

### Creating offset-path using xywh() 

In the example below, the [`offset-path`](../offset-path) property uses
the `xywh()` function to define the shape of the path on which the
element, a magenta box in this case, moves. Two different scenarios are
shown, each with different values for the `xywh()` function. The arrow
inside the boxes points to the right edge of the box.

[html]

```html
<div class="container">
  Rectangular path 1
  <div class="path xywh-path-1">→</div>
</div>
<div class="container">
  Rectangular path 2
  <div class="path xywh-path-2">→</div>
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
  margin: 30px;
  text-align: center;
}

.path {
  width: 50px;
  height: 50px;
  position: absolute;
  background-color: magenta;
  animation: move 10s linear infinite;
}

.xywh-path-1 {
  offset-path: xywh(20px 20px 100% 100% round 10%);
}
```css
.xywh-path-2 {
  offset-path: xywh(20px 30% 150% 200%);
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

- The path 1 rectangle is offset by `20px` from the left and top edges
    of the containing block. This path rectangle has the same dimension
    as the containing block, that is, the width is `100%` of the width
    of the containing block, and the height is `100%` of the height of
    the containing block. Notice how the arrow inside the box follows
    the `10%` curve (defined by `round 10%`) at the rectangular path
    corners.
- As the upper limit of both width and height in `xywh()` is infinity,
    setting the height to `200%` in the path 2 rectangle makes the
    generated rectangle twice as tall as the containing block. Notice
    how the arrow inside the box behaves at the corners when no
    `round <'border-radius'>` is specified.

Specifications
--------------

  -----------------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------------

  [CSS Shapes Module Level 1\
  [\#
  funcdef-basic-shape-xywh]](https://drafts.csswg.org/css-shapes-1/#funcdef-basic-shape-xywh)

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

`xywh`

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
- [`rect()`](basic-shape.md#rect) function
- [`clip-path`](clip-path.md) property
- [`offset-path`](offset-path.md) property
- [`<basic-shape>`](basic-shape.md) data type
- [CSS shapes](css_shapes.md) module
- [Guide to basic shapes](basic_shapes.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/basic-shape/xywh>
