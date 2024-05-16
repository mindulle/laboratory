rotateY()
=========

The `rotateY()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) defines a transformation that rotates an
element around the y-axis (vertical) without deforming it. Its result is
a [`<transform-function>`](transform-function.md) data type.

Try it
------

The axis of rotation passes through an origin, defined by the
[`transform-origin`](transform-origin.md) CSS property.

**Note:** `rotateY(a)` is equivalent to `rotate3d(0, 1, 0, a)`.

**Note:** Unlike rotations in the 2D plane, the composition of 3D
rotations is usually not commutative. In other words, the order in which
the rotations are applied impacts the result.

Syntax
------

The amount of rotation created by `rotateY()` is specified by an
[`<angle>`](angle.md). If positive, the movement will be clockwise; if
negative, it will be counter-clockwise.

[css]

```css
rotateY(a)
```

### Values

[`a`](#a)

:   Is an [`<angle>`](angle.md) representing the angle of the rotation.
    A positive angle denotes a clockwise rotation, a negative angle a
    counter-clockwise one.

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
 \\
0 & 1 & 0 \\
 \\
\end$

$\begin
 & 0 \\
0 & 1 & 0 & 0 \\
 & 0 \\
0 & 0 & 0 & 1 \\
\end$

Examples
--------

### HTML

[html]

```html
<div>Normal</div>
<div class="rotated">Rotated</div>
```

### CSS

[css]

```css
div {
  width: 80px;
  height: 80px;
  background-color: skyblue;
}

.rotated {
  transform: rotateY(60deg);
  background-color: pink;
}
```

### Result

Specifications
--------------

  ---------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------

  [CSS Transforms Module Level 2\
  [\#
  funcdef-rotatey]](https://drafts.csswg.org/css-transforms-2/#funcdef-rotatey)

  ---------------------------------------------------------------------------------------

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

`rotateY`

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

- [`transform`](transform.md) property
- [`rotate`](_Resources/Markup%20And%20Styling/css/rotate.md) property
- [`<transform-function>`](transform-function.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/rotateY>
