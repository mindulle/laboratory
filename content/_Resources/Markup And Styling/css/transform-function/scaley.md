scaleY()
========

The `scaleY()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) defines a transformation that resizes an
element along the y-axis (vertically). Its result is a
[`<transform-function>`](transform-function.md) data type.

Try it
------

It modifies the ordinate (vertical, y-coordinate) of each element point
by a constant factor, except when the scale factor is 1, in which case
the function is the identity transform. The scaling is not isotropic,
and the angles of the element are not conserved. `scaleY(-1)` defines an
[axial symmetry](https://en.wikipedia.org/wiki/Axial_symmetry), with a
horizontal axis passing through the origin (as specified by the
[`transform-origin`](transform-origin.md) property).

**Note:** `scaleY(sy)` is equivalent to `scale(1, sy)` or
`scale3d(1, sy, 1)`.

`transform: rotateX(180deg);` === `transform: scaleY(-1);`

Syntax
------

[css]

```css
scaleY(s)
```

### Values

[`s`](#s)

:   Is a [`<number>`](number.md) representing the scaling factor to
    apply on the ordinate (vertical, y-coordinate) of each point of the
    element.

[Cartesian coordinates](transform-function.md#cartesian_coordinates) on
[ℝ\^2](https://en.wikipedia.org/wiki/Real_coordinate_space)

[Homogeneous
coordinates](https://en.wikipedia.org/wiki/Homogeneous_coordinates) on
[ℝℙ\^2](https://en.wikipedia.org/wiki/Real_projective_plane)

Cartesian coordinates on
[ℝ\^3](https://en.wikipedia.org/wiki/Real_coordinate_space)

Homogeneous coordinates on
[ℝℙ\^3](https://en.wikipedia.org/wiki/Real_projective_space)

$\begin
1 & 0 \\
0 & s \\
\end$

$\begin
1 & 0 & 0 \\
0 & s & 0 \\
0 & 0 & 1 \\
\end$

$\begin
1 & 0 & 0 \\
0 & s & 0 \\
0 & 0 & 1 \\
\end$

$\begin
1 & 0 & 0 & 0 \\
0 & s & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 1 \\
\end$

`[1 0 0 s 0 0]`

Examples
--------

### HTML

[html]

```html
<div>Normal</div>
<div class="scaled">Scaled</div>
```

### CSS

[css]

```css
div {
  width: 80px;
  height: 80px;
  background-color: skyblue;
}

.scaled {
  transform: scaleY(0.6);
  background-color: pink;
}
```

### Result

Specifications
--------------

  -------------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------------

  [CSS Transforms Module Level 1\
  [\#
  funcdef-transform-scaley]](https://drafts.csswg.org/css-transforms/#funcdef-transform-scaley)

  -------------------------------------------------------------------------------------------------------

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

`scaleY`

1

12

3.5

9

10.5

3.1

2

18

4

11

3.2

1.0

See also
--------

- [`scaleX()`](scalex.md)
- [`scaleZ()`](scalez.md)
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
https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/scaleY>
