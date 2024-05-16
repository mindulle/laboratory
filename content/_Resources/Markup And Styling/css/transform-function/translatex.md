translateX()
============

The `translateX()`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) repositions an element horizontally on the
2D plane. Its result is a
[`<transform-function>`](transform-function.md) data type.

Try it
------

**Note:** `translateX(tx)` is equivalent to `translate(tx, 0)` or
`translate3d(tx, 0, 0)`.

Syntax
------

[css]

```css
/* <length-percentage> values */
transform: translateX(200px);
transform: translateX(50%);
```

### Values

[`<length-percentage>`](#length-percentage)

:   Is a [`<length>`](length.md) or [`<percentage>`](percentage.md)
    representing the abscissa (horizontal, x-component) of the
    translating vector \[tx, 0\]. In [](transform-function.md#cartesian_coordinates) it represents
    shift along x-axis. A percentage value refers to the width of the
    reference box defined by the [`transform-box`](transform-box.md)
    property.

[Cartesian coordinates](transform-function.md#cartesian_coordinates) on
[ℝ\^2](https://en.wikipedia.org/wiki/Real_coordinate_space)

[Homogeneous
coordinates](https://en.wikipedia.org/wiki/Homogeneous_coordinates) on
[ℝℙ\^2](https://en.wikipedia.org/wiki/Real_projective_plane)

Cartesian coordinates on
[ℝ\^3](https://en.wikipedia.org/wiki/Real_coordinate_space)

Homogeneous coordinates on
[ℝℙ\^3](https://en.wikipedia.org/wiki/Real_projective_space)

A translation is not a linear transformation in ℝ\^2 and can\'t be
represented using a Cartesian-coordinate matrix.

$\begin
1 & 0 & t \\
0 & 1 & 0 \\
0 & 0 & 1 \\
\end$

$\begin
1 & 0 & t \\
0 & 1 & 0 \\
0 & 0 & 1 \\
\end$

$\begin
1 & 0 & 0 & t \\
0 & 1 & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 1 \\
\end$

`[1 0 0 1 t 0]`

### Formal syntax

[css]

```css
translateX(<length-percentage>)
```

Examples
--------

### HTML

[html]

```html
<div>Static</div>
<div class="moved">Moved</div>
<div>Static</div>
```

### CSS

[css]

```css
div {
  width: 60px;
  height: 60px;
  background-color: skyblue;
}

.moved {
  transform: translateX(10px); /* Equal to translate(10px) */
  background-color: pink;
}
```

### Result

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------------

  [CSS Transforms Module Level 1\
  [\#
  funcdef-transform-translatex]](https://drafts.csswg.org/css-transforms/#funcdef-transform-translatex)

  ---------------------------------------------------------------------------------------------------------------

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

`translateX`

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

- [`translate()`](_Resources/Markup%20And%20Styling/css/transform-function/translate.md)
- [`translateY()`](translatey.md)
- [`transform`](transform.md)
- [`<transform-function>`](transform-function.md)
- [`translate`](_Resources/Markup%20And%20Styling/css/translate.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/translateX>
