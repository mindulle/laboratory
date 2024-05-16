scaleZ()
========

The `scaleZ()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) defines a transformation that resizes an
element along the z-axis. Its result is a
[`<transform-function>`](transform-function.md) data type.

Try it
------

This scaling transformation modifies the z-coordinate of each element
point by a constant factor, except when the scale factor is 1, in which
case the function is the identity transform. The scaling is not
isotropic, and the angles of the element are not conserved. `scaleZ(-1)`
defines an [axial
symmetry](https://en.wikipedia.org/wiki/Axial_symmetry), with the z-axis
passing through the origin (as specified by the
[`transform-origin`](transform-origin.md) property).

In the above interactive examples,
[`perspective: 550px;`](_Resources/Markup%20And%20Styling/css/perspective.md) (to create a 3D space) and
[`transform-style: preserve-3d;`](transform-style.md) (so the children,
the 6 sides of the cube, are also positioned in the 3D space), have been
set on the cube.

**Note:** `scaleZ(sz)` is equivalent to `scale3d(1, 1, sz)`.

Syntax
------

[css]

```css
scaleZ(s)
```

### Values

[`s`](#s)

:   Is a [`<number>`](number.md) representing the scaling factor to
    apply on the z-coordinate of each point of the element.

[Cartesian coordinates](transform-function.md#cartesian_coordinates) on
[ℝ\^2](https://en.wikipedia.org/wiki/Real_coordinate_space)

[Homogeneous
coordinates](https://en.wikipedia.org/wiki/Homogeneous_coordinates) on
[ℝℙ\^2](https://en.wikipedia.org/wiki/Real_projective_plane)

Cartesian coordinates on
[ℝ\^3](https://en.wikipedia.org/wiki/Real_coordinate_space)

Homogeneous coordinates on
[ℝℙ\^3](https://en.wikipedia.org/wiki/Real_projective_space)

This transformation applies to the 3D space and can\'t be represented on
the plane.

$\begin
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & s \\
\end$

$\begin
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & s & 0 \\
0 & 0 & 0 & 1 \\
\end$

Examples
--------

### HTML

[html]

```html
<div>Normal</div>
<div class="perspective">Translated</div>
<div class="scaled-translated">Scaled</div>
```

### CSS

[css]

```css
div {
  width: 80px;
  height: 80px;
  background-color: skyblue;
}

.perspective {
  /* Includes a perspective to create a 3D space */
  transform: perspective(400px) translateZ(-100px);
  background-color: limegreen;
}

.scaled-translated {
  /* Includes a perspective to create a 3D space */
  transform: perspective(400px) scaleZ(2) translateZ(-100px);
  background-color: pink;
}
```

### Result

Specifications
--------------

  -------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------

  [CSS Transforms Module Level 2\
  [\#
  funcdef-scalez]](https://drafts.csswg.org/css-transforms-2/#funcdef-scalez)

  -------------------------------------------------------------------------------------

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

`scaleZ`

12

12

10

10

15

4

3

18

10

14

3.2

1.0

See also
--------

- [`scaleX()`](scalex.md)
- [`scaleY()`](scaley.md)
- [`transform`](transform.md)
- [`<transform-function>`](transform-function.md)
- [`transform-origin`](transform-origin.md)
- Individual transform properties:
  - [`translate`](_Resources/Markup%20And%20Styling/css/translate.md)
  - [`scale`](_Resources/Markup%20And%20Styling/css/scale.md)
  - [`rotate`](_Resources/Markup%20And%20Styling/css/rotate.md)
  - Note: there is no `skew` property

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/scaleZ>
