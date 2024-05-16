translate()
===========

The `translate()`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) repositions an element in the horizontal
and/or vertical directions. Its result is a
[`<transform-function>`](transform-function.md) data type.

Try it
------

This transformation is characterized by a two-dimensional vector \[tx,
ty\]. Its coordinates define how much the element moves in each
direction.

Syntax
------

[css]

```css
/* Single <length-percentage> values */
transform: translate(200px);
transform: translate(50%);

/* Double <length-percentage> values */
transform: translate(100px, 200px);
transform: translate(100px, 50%);
transform: translate(30%, 200px);
transform: translate(30%, 50%);
```

### Values

[Single](#single) `<length-percentage>` values

:   This value is a [`<length>`](length.md) or
    [`<percentage>`](percentage.md) representing the abscissa
    (horizontal, x-component) of the translating vector \[tx, 0\]. The
    ordinate (vertical, y-component) of the translating vector will be
    set to `0`. For example, `translate(2px)` is equivalent to
    `translate(2px, 0)`. A percentage value refers to the width of the
    reference box defined by the [`transform-box`](transform-box.md)
    property.

[Double](#double) `<length-percentage>` values

:   This value describes two [`<length>`](length.md) or
    [`<percentage>`](percentage.md) values representing both the
    abscissa (horizontal, x-component) and the ordinate (vertical,
    y-component) of the translating vector \[tx, ty\]. A percentage as
    first value refers to the width, as second part to the height of the
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
1 & 0 &  \\
0 & 1 &  \\
0 & 0 & 1 \\
\end$

$\begin
1 & 0 &  \\
0 & 1 &  \\
0 & 0 & 1 \\
\end$

$\begin
1 & 0 & 0 &  \\
0 & 1 & 0 &  \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 1 \\
\end$

`[1 0 0 1 tx ty]`

### Formal syntax

[css]

```css
translate(<length-percentage>, <length-percentage>?)
```

Examples
--------

### Using a single-axis translation

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
  /* Equal to: translateX(10px) or translate(10px, 0) */
  transform: translate(10px);
  background-color: pink;
}
```

#### Result

### Combining y-axis and x-axis translation

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
  transform: translate(10px, 10px);
  background-color: pink;
}
```

#### Result

Specifications
--------------

  -------------------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------------------

  [CSS Transforms Module Level 1\
  [\#
  funcdef-transform-translate]](https://drafts.csswg.org/css-transforms/#funcdef-transform-translate)

  -------------------------------------------------------------------------------------------------------------

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

`translate`

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
- [`translate`](_Resources/Markup%20And%20Styling/css/translate.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/translate>
