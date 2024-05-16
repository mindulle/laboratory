translate3d()
=============

The `translate3d()`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) repositions an element in 3D space. Its
result is a [`<transform-function>`](transform-function.md) data type.

Try it
------

This transformation is characterized by a three-dimensional vector \[tx,
ty, tz\]. Its coordinates define how much the element moves in each
direction.

Syntax
------

[css]

```css
translate3d(tx, ty, tz)
```

### Values

[`tx`](#tx)

:   Is a [`<length>`](length.md) or [`<percentage>`](percentage.md)
    representing the abscissa (horizontal, x-component) of the
    translating vector \[tx, ty, tz\].

[`ty`](#ty)

:   Is a [`<length>`](length.md) or [`<percentage>`](percentage.md)
    representing the ordinate (vertical, y-component)of the translating
    vector \[tx, ty, tz\].

[`tz`](#tz)

:   Is a [`<length>`](length.md) representing the z-component of the
    translating vector. It can\'t be a [`<percentage>`](percentage.md)
    value; in that case the property containing the transform is
    considered invalid \[tx, ty, tz\].

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

A translation is not a linear transformation in ℝ\^3 and can\'t be
represented using a Cartesian-coordinate matrix.

$\begin
1 & 0 & 0 &  \\
0 & 1 & 0 &  \\
0 & 0 & 1 &  \\
0 & 0 & 0 & 1 \\
\end$

Examples
--------

### Using a single axis translation

#### HTML

[html]

```html
<div>Static</div>
<div class="moved">Moved</div>
<div>Static</div>
```

#### CSS

[css]

```css
div {
  width: 60px;
  height: 60px;
  background-color: skyblue;
}

.moved {
  /* Equivalent to perspective(500px) translateX(10px) */
  transform: perspective(500px) translate3d(10px, 0, 0px);
  background-color: pink;
}
```

#### Result

### Combining z-axis and x-axis translation

#### HTML

[html]

```html
<div>Static</div>
<div class="moved">Moved</div>
<div>Static</div>
```

#### CSS

[css]

```css
div {
  width: 60px;
  height: 60px;
  background-color: skyblue;
}

.moved {
  transform: perspective(500px) translate3d(10px, 0, 100px);
  background-color: pink;
}
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------

  [CSS Transforms Module Level 2\
  [\#
  funcdef-translate3d]](https://drafts.csswg.org/css-transforms-2/#funcdef-translate3d)

  -----------------------------------------------------------------------------------------------

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

`translate3d`

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
- [`translate`](_Resources/Markup%20And%20Styling/css/translate.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/translate3d>
