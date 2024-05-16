ray()
=====

**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.

The `ray()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) defines the [`offset-path`](offset-path.md) line
segment that an animated element can follow. The line segment is
referred to as \"ray\". The ray begins from an
[`offset-position`](offset-position.md) and extends in the direction of the
specified angle. The length of a ray can be constrained by specifying a
size and using the `contain` keyword.

[css]

```css
ray() = ray( <angle> && <size>? && contain? && [at <position>]? )
<size> = closest-side | closest-corner | farthest-side | farthest-corner | sides
```

Syntax
------

[css]

```css
/* offset-path: ray(parameters) */

/* all parameters specified */
offset-path: ray(50deg closest-corner contain at 100px 20px);

/* two parameters specified, order does not matter */
offset-path: ray(contain 200deg);

/* only one parameter specified */
offset-path: ray(45deg);
```

### Parameters

The parameters can be specified in any order.

[`<angle>`](angle.md)

:   Specifies the direction in which the line segment extends from the
    offset starting position. The angle `0deg` lies on the y-axis
    pointing up, and positive angles increase in the clockwise
    direction.

[`<size>`](#size)

:   Specifies the length of the line segment, which is the distance
    between [`offset-distance`](offset-distance.md) `0%` and `100%`,
    relative to the containing box. It is an optional parameter
    (`closest-side` is used if no `<size>` is specified) and accepts one
    of the following keyword values:

    `closest-side`: Distance between the ray\'s starting point and the
    closest side of the [containing block](containing_block) of the
    element. If the ray\'s starting point lies on an edge of the
    containing block, the length of the line segment is zero. If the
    ray\'s starting point is outside the containing block, the edge of
    the containing block is considered to extend to infinity.

    `closest-corner`: Distance between the ray\'s starting point and the
    closest corner in the element\'s containing block. If the ray\'s
    starting point lies on a corner of the containing block, the length
    of the line segment is zero.

    `farthest-side`: Distance between the ray\'s starting point and the
    farthest side of the containing block of the element. If the ray\'s
    starting point is outside the containing block, the edge of the
    containing block is considered to extend to infinity.

    `farthest-corner`: Distance between the ray\'s starting point and
    the farthest corner in the element\'s containing block.

    `sides`: Distance between the ray\'s starting point and the point
    where the line segment intersects the containing block\'s boundary.
    If the starting point is on or outside the containing block\'s
    boundary, the length of the line segment is zero.

**Note:** While the size parameter is optional in the specification,
some browsers implement `ray()` with a required size value. Including
the default `closest-side` is the equivalent of omitting the size, but
has better support.

[`contain`](#contain)

:   Reduces the length of the line segment so that the element stays
    within the containing block even at `offset-distance: 100%`.
    Specifically, the segment\'s length is reduced by half the width or
    half the height of the element\'s border box, whichever is greater,
    but never going less than zero. It is an optional parameter.

[`at <position>`](#at_position)

:   Specifies the point where the ray begins and where the element is
    placed in its containing block. This is an optional parameter. If
    omitted, the value used is the `offset-position` value of the
    element. If omitted and the element doesn\'t have an
    `offset-position` value, the value used for ray\'s starting position
    is `offset-position: auto`, which places the element at the
    `top left` corner of the element\'s box.

Description
-----------

The `ray()` function allows the positioning of an element along a path
using polar coordinates, rather than using the standard rectangular
coordinates used by the [`translate()`](_Resources/Markup%20And%20Styling/css/translate.md) function or using
animation to move an element along a defined path. The `ray()` function
helps to create 2D spatial transitions.

The element is initially positioned by moving the element\'s
[`offset-anchor`](offset-anchor.md) point to the element\'s offset starting
position. The default offset starting position of a ray is the default
`offset-position` value: `auto`. If `offset-position` is explicitly
specified as `auto` or omitted and allowed to default, the offset
starting position is the `top left` corner (or `0 0`) of the element\'s
box. With `offset-position: normal`, the starting position of the ray is
`50%, 50%` of the element\'s containing block.

The `<coord-box>` value of the [`offset-path`](offset-path.md) property
provides the reference box for the ray path.

Examples
--------

### Defining the angle and starting position for a ray

This example shows how to work with an element\'s anchor point, how the
element gets oriented at the specified ray angle, and how to change a
ray\'s starting point.

#### CSS

[css]

```css
.box {
  background-color: palegreen;
  border-top: 4px solid black;
  position: absolute;
  opacity: 20%;
}

.box1 {
  offset-path: ray(0deg closest-side);
}

.box2 {
  offset-anchor: 0 0;
  offset-path: ray(0deg closest-side);
}

.box3 {
  offset-anchor: 0 0;
  offset-path: ray(150deg closest-side);
}

.box4 {
  offset-rotate: 0deg;
  offset-anchor: 0 0;
  offset-position: 20% 30%;
  offset-path: ray(closest-side 150deg);
}

.box5 {
  offset-rotate: 0deg;
  offset-path: ray(100deg closest-side at bottom right);
}
```

Similar to [`transform-origin`](transform-origin.md), the default anchor
point is at the center of an element. This anchor point can be modified
using the [`offset-anchor`](offset-anchor.md) property.

In this example, various `offset-anchor` and `offset-path: ray()` values
are applied to a box. Results are displayed side-by-side for comparison.
The element\'s containing block is depicted with a dashed border. One
border of the box is highlighted to demonstrate different ray starting
points and box orientations. After a box is positioned at the ray\'s
starting point, it is oriented in the direction of the specified ray
angle. If `offset-position` is not specified, the default offset
starting position of a ray is the top-left corner of the element\'s
containing block.

#### Result

- `box1` gets initially positioned such that its anchor point (at the
    center) is at the offset starting position (top-left corner of the
    box). `box1` is also rotated to orient it towards the `0deg` angle
    of the ray. This will now be the starting point of the path. You can
    observe the change in position and rotation of the box by comparing
    it to the faded `box0` in the background.
- The anchor point of `box2` is changed to the top-left corner
    (`0px 0px`) using the `offset-anchor` property, and as a result, the
    element\'s anchor point and the offset starting position coincide.
    The ray angle is applied to the element at this starting point. The
    box is rotated to match the `0deg` angle along y-axis and pointing
    up.
- With other settings the same as in `box2`, a greater positive angle
    of `150deg` is applied in `box3`. Starting from the top-left corner,
    the box is rotated in a clockwise direction to reach the specified
    angle of `150deg`.
- `box3` and `box4` have the same `offset-anchor` and `offset-path`
    values. In `box4`, however, an [`offset-rotate`](offset-rotate.md) of
    `0deg` is applied to the element. As a result, the element will
    remain rotated at this specific angle all along the ray\'s path, and
    the element will not rotate in the direction of the path. Notice in
    `box4` that the ray path is at `150deg`, but the box orientation
    will not change along the path because of `offset-rotate`. Also note
    that the `offset-path` property of `box4` does not specify a
    starting `<position>`, so the ray\'s starting position is derived
    from the element\'s `offset-position`, which in this case is
    `top 20% left 30%`.
- In `box5`, the `offset-path` property specifies the `at <position>`
    value, which places the box at the `bottom` and `right` edge of the
    element\'s containing block.

### Animating an element along the ray

In this example, the first shape is shown as a reference for its
position and orientation. A ray motion path is applied on the other
shapes.

#### CSS

[css]

```css
body {
  display: grid;
  grid-template-columns: 200px 100px;
  gap: 40px;
  margin-left: 40px;
}

.container {
   transform-style: preserve-3d;
   width: 150px;
   height: 100px;
   border: 2px dotted green;
}

.shape {
  width: 40px;
  height: 40px;
  background: #2bc4a2;
  margin: 5px;
  text-align: center;
  line-height: 40px;
  clip-path: polygon(0% 0%, 70% 0%, 100% 50%, 70% 100%, 0% 100%, 30% 50%);
  animation: move 5000ms infinite alternate ease-in-out;
}

.shape2 {
  offset-path: ray(120deg sides contain);
}

.shape3 {
  offset-rotate: 0deg;
  offset-path: ray(120deg sides contain);
}

.shape4 {
  offset-path: ray(120deg closest-corner);
}

.shape5 {
  offset-path: ray(120deg farthest-corner);
}

@keyframes move {
  0%, 20% {
    offset-distance: 0%;
  }
  80%, 100% {
    offset-distance: 100%;
  }
```

#### Result

In the first two samples where `offset-path` is applied, notice the
orientation of the shape without `offset-rotate` and with
`offset-rotate`. The last two `offset-path` samples show the impact of
corner `<size>` values: `closest-corner` and `farthest-corner`. The
`closest-corner` value creates a very short offset-path because the
shape is already at the corner. The `farthest-corner` value creates the
longest offset-path, going from the top-left corner of the containing
block to the bottom-right corner.

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [Motion Path Module Level 1\
  [\#
  ray-function]](https://drafts.fxtf.org/motion/#ray-function)

  -----------------------------------------------------------------------

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

`ray`

116

116

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

`position`

116

116

116`<at-position>` is optional. If omitted, the `offset-position` of the
element is used.

No

102

No

116

116

No

No

No

No

`size`

116

116

112`<size>` is optional. If omitted, the value `closest-side` is used.

72`<size>` is required.

No

102

No

116

116

No

No

No

No

See also
--------

- [`offset-distance`](offset-distance.md)
- [`offset-path`](offset-path.md)
- [`offset-rotate`](offset-rotate.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/ray>
