rotate()
========

The `rotate()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) defines a transformation that rotates an
element around a fixed point on the 2D plane, without deforming it. Its
result is a [`<transform-function>`](transform-function.md) data type.

Try it
------

The fixed point that the element rotates around --- mentioned above ---
is also known as the **transform origin**. This defaults to the center
of the element, but you can set your own custom transform origin using
the [`transform-origin`](transform-origin.md) property.

Syntax
------

The amount of rotation created by `rotate()` is specified by an
[`<angle>`](angle.md). If positive, the movement will be clockwise; if
negative, it will be counter-clockwise. A rotation by 180° is called
*point reflection*.

[css]

```css
rotate(a)
```

### Values

[*a*](#a)

:   Is an [`<angle>`](angle.md) representing the angle of the rotation.
    The direction of rotation depends on the writing direction. In a
    left-to-right context, a positive angle denotes a clockwise
    rotation, a negative angle a counter-clockwise one. In a
    right-to-left context, a positive angle denotes a counter-clockwise
    rotation, a negative angle a clockwise one.

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
 \\
 \\
\end$

$\begin
 & 0 \\
 & 0 \\
0 & 0 & 1 \\
\end$

$\begin
 & 0 \\
 & 0 \\
0 & 0 & 1 \\
\end$

$\begin
 & 0 & 0 \\
 & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 1 \\
\end$

`[cos(a) sin(a) -sin(a) cos(a) 0 0]`

Examples
--------

### Basic example

#### HTML

[html]

```html
<div>Normal</div>
<div class="rotated">Rotated</div>
```

#### CSS

[css]

```css
div {
  width: 80px;
  height: 80px;
  background-color: skyblue;
}

.rotated {
  transform: rotate(45deg); /* Equal to rotateZ(45deg) */
  background-color: pink;
}
```

#### Result

### Combining rotation with another transformation

If you want to apply multiple transformations to an element, be careful
about the order in which you specify your transformations. For example,
if you rotate before translating, the translation will be along the new
axis of rotation!

#### HTML

[html]

```html
<div>Normal</div>
<div class="rotate">Rotated</div>
<div class="rotate-translate">Rotated + Translated</div>
<div class="translate-rotate">Translated + Rotated</div>
```

#### CSS

[css]

```css
div {
  position: absolute;
  left: 40px;
  top: 40px;
  width: 100px;
  height: 100px;
  background-color: lightgray;
}

.rotate {
  background-color: transparent;
  outline: 2px dashed;
  transform: rotate(45deg);
}

.rotate-translate {
  background-color: pink;
  transform: rotate(45deg) translateX(180px);
}

.translate-rotate {
  background-color: gold;
  transform: translateX(180px) rotate(45deg);
}
```

#### Result

Specifications
--------------

  -------------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------------

  [CSS Transforms Module Level 1\
  [\#
  funcdef-transform-rotate]](https://drafts.csswg.org/css-transforms/#funcdef-transform-rotate)

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

`rotate`

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

- [`transform`](transform.md) property
- [`rotate`](_Resources/Markup%20And%20Styling/css/rotate.md) property
- [`<transform-function>`](transform-function.md)
- [`rotate3d()`](rotate3d.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/rotate>
