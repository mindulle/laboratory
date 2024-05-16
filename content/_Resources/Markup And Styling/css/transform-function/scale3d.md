scale3d()
=========

The `scale3d()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) defines a transformation that resizes an
element in 3D space. Because the amount of scaling is defined by a
vector \[sx, sy, sz\], it can resize different dimensions at different
scales. Its result is a [`<transform-function>`](transform-function.md)
data type.

Try it
------

This scaling transformation is characterized by a three-dimensional
vector. Its coordinates define how much scaling is done in each
direction. If all three coordinates are equal, the scaling is uniform
(*isotropic*) and the aspect ratio of the element is preserved (this is
a [homothetic
transformation](https://en.wikipedia.org/wiki/Homothetic_transformation)).

When a coordinate value is outside the \[-1, 1\] range, the element
grows along that dimension; when inside, it shrinks. If it is negative,
the result a [point
reflection](https://en.wikipedia.org/wiki/Point_reflection) in that
dimension. A value of 1 has no effect.

Syntax
------

The `scale3d()` function is specified with three values, which represent
the amount of scaling to be applied in each direction.

[css]

```css
scale3d(sx, sy, sz)
```

### Values

[`sx`](#sx)

:   Is a [`<number>`](number.md) representing the abscissa (horizontal,
    x-component) of the scaling vector.

[`sy`](#sy)

:   Is a [`<number>`](number.md) representing the ordinate (vertical,
    y-component) of the scaling vector.

[`sz`](#sz)

:   Is a [`<number>`](number.md) representing the z-component of the
    scaling vector.

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
 & 0 & 0 \\
0 &  & 0 \\
0 & 0 &  \\
\end$

$\begin
 & 0 & 0 & 0 \\
0 &  & 0 & 0 \\
0 & 0 &  & 0 \\
0 & 0 & 0 & 1 \\
\end$

Examples
--------

### Without changing the origin

#### HTML

[html]

```html
<div>Normal</div>
<div class="scaled">Scaled</div>
```

#### CSS

[css]

```css
div {
  width: 80px;
  height: 80px;
  background-color: skyblue;
}

.scaled {
  transform: perspective(500px) scale3d(2, 0.7, 0.2) translateZ(100px);
  background-color: pink;
}
```

#### Result

### Translating the origin of the transformation

#### HTML

[html]

```html
<div>Normal</div>
<div class="scaled">Scaled</div>
```

#### CSS

[css]

```css
div {
  width: 80px;
  height: 80px;
  background-color: skyblue;
}

.scaled {
  transform: perspective(500px) scale3d(2, 0.7, 0.2) translateZ(100px);
  transform-origin: left;
  background-color: pink;
}
```

#### Result

Specifications
--------------

  ---------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------

  [CSS Transforms Module Level 2\
  [\#
  funcdef-scale3d]](https://drafts.csswg.org/css-transforms-2/#funcdef-scale3d)

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

`scale3d`

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

- [`transform`](transform.md)
- [`<transform-function>`](transform-function.md)
- [`scaleZ()`](scalez.md)
- [`translate3d()`](translate3d.md)
- [`rotate3d()`](rotate3d.md)
- Individual transform properties:
  - [`translate`](_Resources/Markup%20And%20Styling/css/translate.md)
  - [`scale`](_Resources/Markup%20And%20Styling/css/scale.md)
  - [`rotate`](_Resources/Markup%20And%20Styling/css/rotate.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/scale3d>
