offset-path
===========

The `offset-path`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property
specifies a path for an element to follow and determines the element\'s
positioning within the path\'s parent container or the SVG coordinate
system. The path is a line, a curve, or a geometrical shape along which
the element gets positioned or moves.

The `offset-path` property is used in combination with the
[`offset-distance`](offset-distance.md), [`offset-rotate`](offset-rotate.md),
and [`offset-anchor`](offset-anchor.md) properties to control the position
and orientation of the element along a path.

Try it
------

Syntax
------

[css]

```css
/* Default */
offset-path: none;

/* Line segment */
offset-path: ray(45deg closest-side contain);
offset-path: ray(contain 150deg at center center);
offset-path: ray(45deg);

/* URL */
offset-path: url(#myCircle);

/* Basic shape */
offset-path: circle(50% at 25% 25%);
offset-path: ellipse(50% 50% at 25% 25%);
offset-path: inset(50% 50% 50% 50%);
offset-path: polygon(30% 0%, 70% 0%, 100% 50%, 30% 100%, 0% 70%, 0% 30%);
offset-path: path("M 0,200 Q 200,200 260,80 Q 290,20 400,0 Q 300,100 400,200");

/* Coordinate box */
offset-path: content-box;
offset-path: padding-box;
offset-path: border-box;
offset-path: fill-box;
offset-path: stroke-box;
offset-path: view-box;

/* Global values */
offset-path: inherit;
offset-path: initial;
offset-path: revert;
offset-path: revert-layer;
offset-path: unset;
```

### Values

The `offset-path` property takes as its value an `<offset-path>` value,
a [`<coord-box>`](box-edge.md#values) value, or both, or the `none`
keyword. The `<offset-path>` value is a [`ray()`](ray.md) function, a
[`<url>`](url.md) value, or a [`<basic-shape>`](basic-shape.md) value.

[`none`](#none)

:   Specifies that the element does not follow any offset path. The
    `none` value is equivalent to the element not having any [](offset.md). The element\'s movement in this case is
    determined by its default position properties, such as [`top`](top.md)
    and [`left`](left.md), instead of an offset path. This is the default
    value.

[`<offset-path>`](#offset-path)

:   A `ray()` function, a `<url>` value, or a `<basic-shape>` value that
    specifies the geometrical offset path. If omitted, the path shape
    for the `<coord-box>` value is `inset(0 round X)`, where `X` is the
    value of [`border-radius`](border-radius.md) of the element that
    establishes the [containing block](containing_block.md).

    [`ray()`](ray)

    :   Defines a line starting at a set position, of a set length, and
        extending at the specified angle. The `ray()` function accepts
        up to four parameters -- an [`<angle>`](angle), an optional size
        value, the optional keyword `contain`, and an optional
        `at <position>`.

    [`<url>`](url)

    :   Specifies the ID of an [SVG shape
        element](https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/Basic_Shapes).
        The path is the shape of the SVG
        [`<circle>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/circle),
        [`<ellipse>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/ellipse),
        [`<line>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/line),
        [`<path>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/path),
        [`<polygon>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/polygon),
        [`<polyline>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/polyline),
        or
        [`<rect>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/rect)
        element referenced by its `id` in the `url()` function. If the
        URL does not reference a shape element or is otherwise invalid,
        the resolved value for the offset path is `path("M0,0")` (which
        is a valid `<basic-shape>` value).

    [`<basic-shape>`](basic-shape)

    :   Specifies the offset path as the equivalent path of a [CSS basic
        shape function](css_shapes/basic_shapes), such as
        [`circle()`](basic-shape/circle),
        [`ellipse()`](basic-shape/ellipse),
        [`inset()`](basic-shape/inset), [`path()`](path), or
        [`polygon()`](basic-shape/polygon). For example, if the
        `<basic_shape>` is an `ellipse()` function, then the path is the
        outline of the ellipse, starting at the rightmost point of the
        ellipse, proceeding clockwise through a full rotation. For
        `ellipse()` and `circle()`, which accept the `at <position>`
        parameter, if the `<position>` is omitted, the position defaults
        to `center` unless the element has an
        [`offset-position`](offset-position) specified. In this case,
        the `offset-position` value is used for the `at <position>`
        parameter.

[`<coord-box>`](box-edge.md#values)

:   Specifies the size information of the [](basic_shapes.md#the_reference_box) containing the path.
    The reference box is derived from the element that establishes the
    containing block for this element. This parameter is optional. If
    not specified, the default value is `border-box` in CSS contexts. In
    SVG contexts, the value is treated as `view-box`. If `ray()` or
    `<basic-shape>` is used to define the offset path, the `<coord-box>`
    value provides the reference box for the ray or the `<basic-shape>`,
    respectively. If `<url>` is used to define the offset path, the
    `<coord-box>` value provides the viewport and user coordinate system
    for the shape element, with the origin (`0 0`) at the top left
    corner and size being `1px`.

Description
-----------

The `offset-path` property defines a path an animated element can
follow. An offset path is either a specified path with one or multiple
sub-paths or the geometry of a not-styled basic shape. The element\'s
exact position on the offset path is determined by the
[`offset-distance`](offset-distance.md) property. Each shape or path must
define an initial position for the computed value of `0` for
[`offset-distance`](offset-distance.md) and an initial direction which
specifies the rotation of the object to the initial position.

Early versions of the spec called this property `motion-path`. It was
changed to `offset-path` because the property describes static
positions, not motion.

Formal definition
-----------------

  ------------------------------------------------------------------------------------------ ------------------------
  [Initial value](initial_value.md)                                                             `none`
  Applies to                                                                                 transformable elements
  [Inherited](inheritance.md)                                                                   no
  [Computed value](computed_value.md)                                                           as specified
  Animation type                                                                             by computed value type
  Creates [stacking context](stacking_context.md)   yes
  ------------------------------------------------------------------------------------------ ------------------------

Formal syntax
-------------

```
offset-path = 
  none                               |
  <ray()>                            |
  <path()>                           |
  <url>                              |
  [ <basic-shape> && <coord-box>? ]  |
  <coord-box>                        

<url> = 
  url( <string> <url-modifier>* )  |
  src( <string> <url-modifier>* )  

<coord-box> = 
  content-box  |
  padding-box  |
  border-box   |
  fill-box     |
  stroke-box   |
  view-box     
```

Examples
--------

### Creating an offset-path using box-edge positioning

This example demonstrates using various `<coord-box>` values in the
`offset-path` property.

[css]

```css
.box {
  width: 40px;
  height: 20px;
  animation: move 8000ms infinite ease-in-out;
}

.blueBox {
  background-color: blue;
  offset-path: border-box;
  offset-distance: 5%;
}

.greenBox {
  background-color: green;
  offset-path: padding-box;
  offset-distance: 8%;
}

.redBox {
  background-color: red;
  offset-path: content-box;
  offset-distance: 12%;
}

@keyframes move {
  0%,
  20% {
    offset-distance: 0%;
  }
  80%,
  100% {
    offset-distance: 100%;
  }
}
```

In this example, the margin, border, and padding have been purposely
given large values to demonstrate the placement of the blue, green, and
red rectangles on their respective `<coord-box>` edges: border-box,
padding-box, and content-box.

#### Result

### Creating an offset-path using path()

In this example, the
[`<svg>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/svg)
element creates a house with a chimney and also defines two halves of a
scissor. The house and chimney are composed of rectangles and polygons,
and the scissor halves are represented by two distinct path elements. In
the CSS code, the `offset-path` property is used to specify a path to
follow for the two scissor halves. This CSS-defined path is identical to
the one represented by the `<path>` element in the SVG, which is the
outline of the house including the chimney.

[html]

```html
<svg
  xmlns="http://www.w3.org/2000/svg"
  width="700"
  height="450"
  viewBox="350 0 1400 900">
  <title>House and Scissors</title>
  <rect x="595" y="423" width="610" height="377" fill="blue" />
  <polygon points="506,423 900,190 1294,423" fill="yellow" />
  <polygon points="993,245 993,190 1086,190 1086,300" fill="red" />
  <path
    id="house"
    d="M900,190 L993,245 V201 A11,11 0 0,1 1004,190 H1075 A11,11 0 0,1 1086,201 V300 L1294,423 H1216 A11,11 0 0,0 1205,434 V789 A11,11 0 0,1 1194,800 H606 A11,11 0 0,1 595,789 V434 A11,11 0 0,0 584,423 H506 L900,190"
    fill="none"
    stroke="black"
    stroke-width="13"
    stroke-linejoin="round"
    stroke-linecap="round" />
  <path
    id="firstScissorHalf"
    class="scissorHalf"
    d="M30,0 H-10 A10,10 0 0,0 -20,10 A20,20 0 1,1 -40,-10 H20 A10,10 0 0,1 30,0 M-40,20 A10,10 1 0,0 -40,0 A10,10 1 0,0 -40,20 M0,0"
    transform="translate(0,0)"
    fill="green"
    stroke="black"
    stroke-width="5"
    stroke-linejoin="round"
    stroke-linecap="round"
    fill-rule="evenodd" />
  <path
    id="secondScissorHalf"
    class="scissorHalf"
    d="M30,0 H-10 A10,10 0 0,1 -20,-10 A20,20 0 1,0 -40,10 H20 A10,10 0 0,0 30,0 M-40,-20 A10,10 1 0,0 -40,0 A10,10 1 0,0 -40,-20 M0,0"
    transform="translate(0,0)"
    fill="forestgreen"
    stroke="black"
    stroke-width="5"
    stroke-linejoin="round"
    stroke-linecap="round"
    fill-rule="evenodd" />
</svg>
```

[css]

```css
.scissorHalf {
  offset-path: path(
    "M900,190  L993,245 V201  A11,11 0 0,1 1004,190  H1075  A11,11 0 0,1 1086,201  V300  L1294,423 H1216  A11,11 0 0,0 1205,434  V789  A11,11 0 0,1 1194,800  H606  A11,11 0 0,1 595,789  V434  A11,11 0 0,0 584,423  H506 L900,190"
  );
  animation: followpath 4s linear infinite;
}

@keyframes followpath {
  to {
    offset-distance: 100%;
  }
}
```

#### Result

Without the `offset-path` property, the two halves of the scissors would
default to the top-left corner of the canvas. However, by using
`offset-path`, the two scissor halves are aligned with the starting
point of the SVG path, allowing them to move along it.

### Creating an offset-path using url()

This example illustrates how to refer to an SVG shape to define the
shape of the path that an element can follow. The green circle (defined
by `.target`) follows the path of a rectangle, which is defined by
passing the SVG shape\'s ID (`svgRect`) to the `offset-path` property by
using `url()`.

The SVG rectangle that defines the path shape is shown here only to
visually demonstrate that the green circle is indeed following the path
defined by this rectangle.

[html]

```html
<div class="outer">
  <div class="target"></div>
</div>
  <svg width="400" height="200" xmlns="http://www.w3.org/2000/svg" >
    <rect id="svgRect" x="50" y="50" width="200" height="100" />
  </svg>
</div>
```

[css]

```css
.target {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  background-color: green;
  offset-path: url(#svgRect);
  offset-anchor: auto;
  animation: move 5s linear infinite;
}

#svgRect {
  fill: antiquewhite;
  stroke: black;
  stroke-width: 2;
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

Specifications
--------------

  --------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------

  [Motion Path Module Level 1\
  [\#
  offset-path-property]](https://drafts.fxtf.org/motion/#offset-path-property)

  --------------------------------------------------------------------------------------

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

`offset-path`

5546

7979

72

No

4532

15.4

5546

5546

79

4332

15.4

6.0`path()` is the only value type supported.

5.0

`basic-shape`

116

116

116

No

102

No

116

116

No

No

No

No

`coord-box`

116

116

116

No

102

No

116

116

No

No

No

No

`path`

64

79

72

No

51

preview

64

64

79

47

No

9.0

`ray`

116

116

112`<size>` is optional with the default value `closest-side`.

72

No

102

preview

116

116

No

No

No

No

`url`

116

116

118

No

102

17

116

116

No

No

17

No

See also
--------

- [`offset`](offset.md)
- [`offset-distance`](offset-distance.md)
- [`offset-rotate`](offset-rotate.md)
- [SVG
    \<path\>](https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/Paths)
- [`path()`](path.md)
- Other demos:
  - [Examples using various shapes
        values](https://codepen.io/team/css-tricks/pen/WZdKMq) on
        Codepen by CSS-Tricks
  - [Moving a triangle along a curved
        path](https://codepen.io/ericwilligers/pen/jMbJPp) on Codepen by
        Eric Willigers
  - [Moving a pair of scissors along the shape of a
        house](https://codepen.io/ericwilligers/pen/bwVZNa) on Codepen
        by Eric Willigers
  - [Moving multiple pairs of
        eyes](https://jsfiddle.net/ericwilligers/r1snqdan/) on JSFiddle
        by Eric Willigers

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/offset-path>
