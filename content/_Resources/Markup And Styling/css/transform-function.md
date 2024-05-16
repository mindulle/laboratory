\<transform-function\>
======================

The `<transform-function>`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [](css_types.md) represents a transformation that affects an element\'s
appearance. Transformation [functions](css_functions.md) can rotate,
resize, distort, or move an element in 2D or 3D space. It is used in the
[`transform`](transform.md) property.

Syntax
------

The `<transform-function>` data type is specified using one of the
transformation functions listed below. Each function applies a geometric
operation in either 2D or 3D.

### Matrix transformation

[`matrix()`](matrix.md)

:   Describes a homogeneous 2D transformation matrix.

[`matrix3d()`](matrix3d.md)

:   Describes a 3D transformation as a 4×4 homogeneous matrix.

### Perspective

[`perspective()`](_Resources/Markup%20And%20Styling/css/transform-function/perspective.md)

:   Sets the distance between the user and the z=0 plane.

### Rotation

[`rotate()`](_Resources/Markup%20And%20Styling/css/transform-function/rotate.md)

:   Rotates an element around a fixed point on the 2D plane.

[`rotate3d()`](rotate3d.md)

:   Rotates an element around a fixed axis in 3D space.

[`rotateX()`](rotatex.md)

:   Rotates an element around the horizontal axis.

[`rotateY()`](rotatey.md)

:   Rotates an element around the vertical axis.

[`rotateZ()`](rotatez.md)

:   Rotates an element around the z-axis.

### Scaling (resizing)

[`scale()`](_Resources/Markup%20And%20Styling/css/transform-function/scale.md)

:   Scales an element up or down on the 2D plane.

[`scale3d()`](scale3d.md)

:   Scales an element up or down in 3D space.

[`scaleX()`](scalex.md)

:   Scales an element up or down horizontally.

[`scaleY()`](scaley.md)

:   Scales an element up or down vertically.

[`scaleZ()`](scalez.md)

:   Scales an element up or down along the z-axis.

### Skewing (distortion)

[`skew()`](skew.md)

:   Skews an element on the 2D plane.

[`skewX()`](skewx.md)

:   Skews an element in the horizontal direction.

[`skewY()`](skewy.md)

:   Skews an element in the vertical direction.

### Translation (moving)

[`translate()`](_Resources/Markup%20And%20Styling/css/transform-function/translate.md)

:   Translates an element on the 2D plane.

[`translate3d()`](translate3d.md)

:   Translates an element in 3D space.

[`translateX()`](translatex.md)

:   Translates an element horizontally.

[`translateY()`](translatey.md)

:   Translates an element vertically.

[`translateZ()`](translatez.md)

:   Translates an element along the z-axis.

Description
-----------

Various coordinate models can be used to describe an HTML element\'s
size and shape, as well as any transformations applied to it. The most
common is the [Cartesian coordinate
system](https://en.wikipedia.org/wiki/Cartesian_coordinate_system),
although [homogeneous
coordinates](https://en.wikipedia.org/wiki/Homogeneous_coordinates) are
also sometimes used.

### Cartesian coordinates

In the Cartesian coordinate system, a two-dimensional point is described
using two values: an x coordinate (abscissa) and a y coordinate
(ordinate). This is represented by the vector notation `(x, y)`.

In CSS (and most computer graphics), the origin `(0, 0)` represents the
*top-left* corner of any element. Positive coordinates are down and to
the right of the origin, while negative ones are up and to the left.
Thus, a point that\'s 2 units to the right and 5 units down would be
`(2, 5)`, while a point 3 units to the left and 12 units up would be
`(-3, -12)`.

### Transformation functions

Transformation functions alter the appearance of an element by
manipulating the values of its coordinates. A linear transformation
function is described using a 2×2 matrix, like this:

$\begin
a & c \\
b & d \\
\end$

The function is applied to an element by using matrix multiplication.
Thus, each coordinate changes based on the values in the matrix:

$\begin
a & c \\
b & d \\
\end
x \\
y \\
\end
 \\
 \\
\end$

It is even possible to apply several transformations in a row:

$\begin
a_ \\
b_ \\
\end
a_ \\
b_ \\
\end
 \\
 \\
\end$

With this notation, it is possible to describe, and therefore compose,
most common transformations: rotations, scaling, or skewing. (In fact,
all transformations that are linear functions can be described.)
Composite transformations are effectively applied in order from right to
left.

However, one major transformation is not linear, and therefore must be
special-cased when using this notation: translation. The translation
vector `(tx, ty)` must be expressed separately, as two additional
parameters.

**Note:** Though trickier than Cartesian coordinates, [homogeneous
coordinates](https://en.wikipedia.org/wiki/Homogeneous_coordinates) in
[projective geometry](https://en.wikipedia.org/wiki/Projective_geometry)
lead to 3×3 transformation matrices, and can express translations as
linear functions.

**Note:** Transform functions are used with the `transform` property but
not with individual transform properties-[`translate`](_Resources/Markup%20And%20Styling/css/translate.md),
[`scale`](_Resources/Markup%20And%20Styling/css/scale.md), and [`rotate`](_Resources/Markup%20And%20Styling/css/rotate.md).

Examples
--------

### Transform function comparison

The following example provides a 3D cube created from DOM elements and
transforms, and a select menu allowing you to choose different transform
functions to transform the cube with, so you can compare the effects of
the different types.

Choose one, and the transform is applied to the cube; after 2 seconds,
the cube reverts back to its starting state. The cube\'s starting state
is slightly rotated using `transform3d()`, to allow you to see the
effect of all the transforms.

#### HTML

[html]

```html
<main>
  <section id="example-element">
    <div class="face front">1</div>
    <div class="face back">2</div>
    <div class="face right">3</div>
    <div class="face left">4</div>
    <div class="face top">5</div>
    <div class="face bottom">6</div>
  </section>

  <div class="select-form">
    <label for="transfunction">Select a transform function</label>
    <select id="transfunction">
      <option selected>Choose a function</option>
      <option>rotate(360deg)</option>
      <option>rotateX(360deg)</option>
      <option>rotateY(360deg)</option>
      <option>rotateZ(360deg)</option>
      <option>rotate3d(1, 1, 1, 90deg)</option>
      <option>scale(1.5)</option>
      <option>scaleX(1.5)</option>
      <option>scaleY(1.5)</option>
      <option>scaleZ(1.5)</option>
      <option>scale3d(1, 1.5, 1.5)</option>
      <option>skew(17deg, 13deg)</option>
      <option>skewX(17deg)</option>
      <option>skewY(17deg)</option>
      <option>translate(100px, 100px)</option>
      <option>translateX(100px)</option>
      <option>translateY(100px)</option>
      <option>translateZ(100px)</option>
      <option>translate3d(50px, 50px, 50px)</option>
      <option>perspective(200px)</option>
      <option>matrix(1, 2, -1, 1, 80, 80)</option>
      <option>matrix3d(1,0,0,0,0,1,3,0,0,0,1,0,50,100,0,1.1)</option>
    </select>
  </div>
</main>
```

#### CSS

[css]

```css
main {
  width: 400px;
  height: 200px;
  padding: 50px;
  background-image: linear-gradient(135deg, white, cyan, white);
}

#example-element {
  width: 100px;
  height: 100px;
  transform-style: preserve-3d;
  transition: transform 1.5s;
  transform: rotate3d(1, 1, 1, 30deg);
}

.face {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  height: 100%;
  position: absolute;
  backface-visibility: inherit;
  font-size: 60px;
  color: #fff;
}

.front {
  background: rgba(90, 90, 90, 0.7);
  transform: translateZ(50px);
}

.back {
  background: rgba(0, 210, 0, 0.7);
  transform: rotateY(180deg) translateZ(50px);
}

.right {
  background: rgba(210, 0, 0, 0.7);
  transform: rotateY(90deg) translateZ(50px);
}

.left {
  background: rgba(0, 0, 210, 0.7);
  transform: rotateY(-90deg) translateZ(50px);
}

.top {
  background: rgba(210, 210, 0, 0.7);
  transform: rotateX(90deg) translateZ(50px);
}

.bottom {
  background: rgba(210, 0, 210, 0.7);
  transform: rotateX(-90deg) translateZ(50px);
}

.select-form {
  margin-top: 50px;
}
```

#### JavaScript

[js]

```js
const selectElem = document.querySelector("select");
const example = document.querySelector("#example-element");

selectElem.addEventListener("change", () => {
  if (selectElem.value === "Choose a function") {
    return;
  } else {
    example.style.transform = `rotate3d(1, 1, 1, 30deg) $`;
    setTimeout(() => {
      example.style.transform = "rotate3d(1, 1, 1, 30deg)";
    }, 2000);
  }
});
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------

  [CSS Transforms Module Level 1\
  [\# transform-functions]](https://drafts.csswg.org/css-transforms/#transform-functions)

[CSS Transforms Module Level 2\
  [\#
  transform-functions]](https://drafts.csswg.org/css-transforms-2/#transform-functions)
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

`transform-function`

1

12

3.5

9Internet Explorer 9 supports 2D but not 3D transforms. In version 9,
mixing 2D and 3D transform functions invalidates the entire property.

10.5

3.1

2

18

4

11

3.2

1.0

`matrix`

1

12

3.5Before Firefox 16, the translation values of `matrix()` could be
[`<length>`](https://developer.mozilla.org/docs/Web/CSS/length)s, in
addition to the standard
[`<number>`](https://developer.mozilla.org/docs/Web/CSS/number).

9

10.5

3.1

2

18

4

11

3.2

1.0

`matrix3d`

12

12

10Before Firefox 16, the translation values of `matrix3d()` could be
[`<length>`](https://developer.mozilla.org/docs/Web/CSS/length)s, in
addition to the standard
[`<number>`](https://developer.mozilla.org/docs/Web/CSS/number).

10

15

4

3

18

10

14

3.2

1.0

`perspective`

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

`rotate3d`

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

`rotateX`

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

`rotateZ`

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

`scale`

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

`scaleX`

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

`skewY`

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

`translateY`

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

`translateZ`

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

- CSS [`transform`](transform.md) property
- Individual transform properties:
  - [`translate`](_Resources/Markup%20And%20Styling/css/translate.md)
  - [`scale`](_Resources/Markup%20And%20Styling/css/scale.md)
  - [`rotate`](_Resources/Markup%20And%20Styling/css/rotate.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function>
