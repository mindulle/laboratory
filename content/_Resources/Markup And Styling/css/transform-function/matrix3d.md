matrix3d()
==========

The `matrix3d()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) defines a 3D transformation as a 4x4
homogeneous matrix. Its result is a
[`<transform-function>`](transform-function.md) data type.

Try it
------

Syntax
------

The `matrix3d()` function is specified with 16 values. They are
described in the column-major order.

[css]

```css
matrix3d(a1, b1, c1, d1, a2, b2, c2, d2, a3, b3, c3, d3, a4, b4, c4, d4)
```

### Values

[*a1*](#sect1) *b1* *c1* *d1* *a2* *b2* *c2* *d2* *a3* *b3* *c3* *d3*

:   Are [`<number>`](number.md)s describing the linear transformation.

[*a4*](#a4) *b4* *c4 d4*

:   Are [`<number>`](number.md)s describing the translation to apply.

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

A generic 3D [affine
transformation](https://en.wikipedia.org/wiki/Affine_transformation)
can\'t be represented using a Cartesian-coordinate matrix, as
translations are not linear transformations.

$\begin
 \\
 \\
 \\
 \\
\end$

Examples
--------

### Cube squashing example

The following example shows a 3D cube created from DOM elements and
transforms, which can be hovered/focused to apply a `matrix3d()`
transform to it.

#### HTML

[html]

```html
<section id="example-element" tabindex="0">
  <div class="face front">1</div>
  <div class="face back">2</div>
  <div class="face right">3</div>
  <div class="face left">4</div>
  <div class="face top">5</div>
  <div class="face bottom">6</div>
</section>
```

#### CSS

[css]

```css
#example-element {
  width: 100px;
  height: 100px;
  transform-style: preserve-3d;
  transition: transform 1.5s;
  transform: rotate3d(1, 1, 1, 30deg);
  margin: 50px auto;
}

#example-element:hover,
#example-element:focus {
  transform: rotate3d(1, 1, 1, 30deg) matrix3d(
      1,
      0,
      0,
      0,
      0,
      1,
      6,
      0,
      0,
      0,
      1,
      0,
      50,
      100,
      0,
      1.1
    );
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
```

#### Result

### Matrix translation and scale example

Another `transform3d()` example, which implements an animated combined
translate and scale.

#### HTML

[html]

```html
<div class="foo">
  Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quos quaerat sit
  soluta, quisquam exercitationem delectus qui unde in facere necessitatibus aut
  quia porro dolorem nesciunt enim, at consequuntur aliquam esse?
</div>
```

#### CSS

[css]

```css
html {
  width: 100%;
}
body {
  height: 100vh;
  /* Centering content */
  display: flex;
  flex-flow: row wrap;
  justify-content: center;
  align-content: center;
}
.foo {
  width: 50%;
  padding: 1em;
  color: white;
  background: #ff8c66;
  border: 2px dashed black;
  text-align: center;
  font-family: system-ui, sans-serif;
  font-size: 14px;
  /* Setting up animation for better demonstration */
  animation: MotionScale 2s alternate linear infinite;
}

@keyframes MotionScale {
  from {
    /*
      Identity matrix is used as basis here.
      The matrix below describes the
      following transformations:
        Translates every X point by -50px
        Translates every Y point by -100px
        Translates every Z point by 0
        Scales down by 10%
    */
    transform: matrix3d(
      1, 0, 0, 0,
      0, 1, 0, 0,
      0, 0, 1, 0,
      -50, -100, 0, 1.1
    );
  }
  50% {
    transform: matrix3d(
      1, 0, 0, 0,
      0, 1, 0, 0,
      0, 0, 1, 0,
      0, 0, 0, 0.9
    );
  }
  to {
     transform: matrix3d(
      1, 0, 0, 0,
      0, 1, 0, 0,
      0, 0, 1, 0,
      50, 100, 0, 1.1
    )
  }
}
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------

  [CSS Transforms Module Level 2\
  [\#
  funcdef-matrix3d]](https://drafts.csswg.org/css-transforms-2/#funcdef-matrix3d)

  -----------------------------------------------------------------------------------------

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

See also
--------

- [`transform`](transform.md)
- Individual transform properties:
  - [`translate`](_Resources/Markup%20And%20Styling/css/translate.md)
  - [`scale`](_Resources/Markup%20And%20Styling/css/scale.md)
  - [`rotate`](_Resources/Markup%20And%20Styling/css/rotate.md)
- [`<transform-function>`](transform-function.md)
- [Understanding the CSS Transforms
    Matrix](https://dev.opera.com/articles/understanding-the-css-transforms-matrix/) (2012)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/matrix3d>
