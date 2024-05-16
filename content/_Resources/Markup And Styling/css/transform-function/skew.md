skew()
======

The `skew()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) defines a transformation that skews an
element on the 2D plane. Its result is a
[`<transform-function>`](transform-function.md) data type.

Try it
------

This transformation is a shear mapping
([transvection](https://en.wikipedia.org/wiki/Shear_mapping)) that
distorts each point within an element by a certain angle in the
horizontal and vertical directions. The effect is as if you grabbed each
corner of the element and pulled them along a certain angle.

The coordinates of each point are modified by a value proportionate to
the specified angle and the distance to the origin. Thus, the farther
from the origin a point is, the greater the value added to it.

Syntax
------

The `skew()` function is specified with either one or two values, which
represent the amount of skewing to be applied in each direction. If you
only specify one value it is used for the x-axis and there will be no
skewing on the y-axis.

[css]

```css
skew(ax)

skew(ax, ay)
```

### Values

[`ax`](#ax)

:   Is an [`<angle>`](angle.md) representing the angle to use to distort
    the element along the x-axis.

[`ay`](#ay)

:   Is an [`<angle>`](angle.md) representing the angle to use to distort
    the element along the y-axis. If not defined, its default value is
    `0`, resulting in a purely horizontal skewing.

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
 & 1 \\
\end$

$\begin
1 &  & 0 \\
 & 1 & 0 \\
0 & 0 & 1 \\
\end$

$\begin
1 &  & 0 \\
 & 1 & 0 \\
0 & 0 & 1 \\
\end$

$\begin
1 &  & 0 & 0 \\
 & 1 & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 1 \\
\end$

`[1 tan(ay) tan(ax) 1 0 0]`

Examples
--------

### Skewing on the x-axis only

#### HTML

[html]

```html
<div>Normal</div>
<div class="skewed">Skewed</div>
```

#### CSS

[css]

```css
body {
  margin: 20px;
}

div {
  width: 80px;
  height: 80px;
  background-color: skyblue;
}

.skewed {
  transform: skew(10deg); /* Equal to skewX(10deg) */
  background-color: pink;
}
```

#### Result

### Skewing on both axes

#### HTML

[html]

```html
<div>Normal</div>
<div class="skewed">Skewed</div>
```

#### CSS

[css]

```css
body {
  margin: 20px;
}

div {
  width: 80px;
  height: 80px;
  background-color: skyblue;
}

.skewed {
  transform: skew(10deg, 10deg);
  background-color: pink;
}
```

#### Result

Specifications
--------------

  ---------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------

  [CSS Transforms Module Level 1\
  [\#
  funcdef-transform-skew]](https://drafts.csswg.org/css-transforms/#funcdef-transform-skew)

  ---------------------------------------------------------------------------------------------------

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

`skew`

1

12

3.5Firefox 14 removed experimental support for `skew()`, but it was
reintroduced in Firefox 15.

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
- [skewX()](skewx.md)
- [skewY()](skewy.md)
- Individual transform properties:
  - [`translate`](_Resources/Markup%20And%20Styling/css/translate.md)
  - [`scale`](_Resources/Markup%20And%20Styling/css/scale.md)
  - [`rotate`](_Resources/Markup%20And%20Styling/css/rotate.md)
  - Note: there is no `skew` property

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/skew>
