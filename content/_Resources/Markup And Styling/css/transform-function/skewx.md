skewX()
=======

The `skewX()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) defines a transformation that skews an
element in the horizontal direction on the 2D plane. Its result is a
[`<transform-function>`](transform-function.md) data type.

Try it
------

This transformation is a shear mapping
([transvection](https://en.wikipedia.org/wiki/Shear_mapping)) that
distorts each point within an element by a certain angle in the
horizontal direction. The abscissa (horizontal, x-coordinate) of each
point is modified by a value proportionate to the specified angle and
the distance to the origin; thus, the farther from the origin a point
is, the greater will be the value added it.

**Note:** `skewX(a)` is equivalent to `skew(a)`.

Syntax
------

[css]

```css
skewX(a)
```

### Values

[`a`](#a)

:   Is an [`<angle>`](angle.md) representing the angle to use to distort
    the element along the abscissa (horizontal, x-coordinate).

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
1 &  \\
0 & 1 \\
\end$

$\begin
1 &  & 0 \\
0 & 1 & 0 \\
0 & 0 & 1 \\
\end$

$\begin
1 &  & 0 \\
0 & 1 & 0 \\
0 & 0 & 1 \\
\end$

$\begin
1 &  & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 1 \\
\end$

`[1 0 tan(a) 1 0 0]`

Examples
--------

### HTML

[html]

```html
<div>Normal</div>
<div class="skewed">Skewed</div>
```

### CSS

[css]

```css
div {
  width: 80px;
  height: 80px;
  background-color: skyblue;
}

.skewed {
  transform: skewX(10deg); /* Equal to skew(10deg) */
  background-color: pink;
}
```

### Result

Specifications
--------------

  -----------------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------------

  [CSS Transforms Module Level 1\
  [\#
  funcdef-transform-skewx]](https://drafts.csswg.org/css-transforms/#funcdef-transform-skewx)

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

`skewX`

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

- [`transform`](transform.md)
- [`<transform-function>`](transform-function.md)
- Individual transform properties:
  - [`translate`](_Resources/Markup%20And%20Styling/css/translate.md)
  - [`scale`](_Resources/Markup%20And%20Styling/css/scale.md)
  - [`rotate`](_Resources/Markup%20And%20Styling/css/rotate.md)
  - Note: there is no `skew` property

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/skewX>
