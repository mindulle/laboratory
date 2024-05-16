translateZ()
============

The `translateZ()`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) repositions an element along the z-axis in
3D space, i.e., closer to or farther away from the viewer. Its result is
a [`<transform-function>`](transform-function.md) data type.

Try it
------

This transformation is defined by a [`<length>`](length.md) which
specifies how far inward or outward the element or elements move.

In the above interactive examples,
[`perspective: 550px;`](_Resources/Markup%20And%20Styling/css/perspective.md) (to create a 3D space) and
[`transform-style: preserve-3d;`](transform-style.md) (so the children,
the 6 sides of the cube, are also positioned in the 3D space), have been
set on the cube.

**Note:** `translateZ(tz)` is equivalent to `translate3d(0, 0, tz)`.

Syntax
------

[css]

```css
translateZ(tz)
```

### Values

[`tz`](#tz)

:   A [`<length>`](length.md) representing the z-component of the
    translating vector \[0, 0, tz\]. In [](transform-function.md#cartesian_coordinates) it represents
    shift along z-axis. A positive value moves the element towards the
    viewer, and a negative value farther away.

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
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 1 & t \\
0 & 0 & 0 & 1 \\
\end$

Examples
--------

In this example, two boxes are created. One is positioned normally on
the page, without being translated at all. The second is altered by
applying perspective to create a 3D space, then moved towards the user.

### HTML

[html]

```html
<div>Static</div>
<div class="moved">Moved</div>
```

### CSS

[css]

```css
div {
  position: relative;
  width: 60px;
  height: 60px;
  left: 100px;
  background-color: skyblue;
}

.moved {
  transform: perspective(500px) translateZ(200px);
  background-color: pink;
}
```

What really matters here is the class \"moved\"; let\'s take a look at
what it does. First, the [`perspective()`](_Resources/Markup%20And%20Styling/css/transform-function/perspective.md) function
positions the viewer relative to the plane that lies where z=0 (in
essence, the surface of the screen). A value of `500px` means the user
is 500 pixels \"in front of\" the imagery located at z=0.

Then, the `translateZ()` function moves the element 200 pixels
\"outward\" from the screen, toward the user. This has the effect of
making the element appear larger when viewed on a 2D display, or closer
when viewed using a VR headset or other 3D display device.

Note if the `perspective()` value is less than the `translateZ()` value,
such as `transform: perspective(200px) translateZ(300px);` the
transformed element will not be visible as it is further than the
user\'s viewport. The smaller the difference between the perspective and
translateZ values, the closer the user is to the element and the larger
the translated element will seem.

**Note:** As the composition of transforms isn\'t commutative, the order
you write the different functions is significant. In particular, in
general, you want `perspective()` to be placed before `translateZ()`.

### Result

Specifications
--------------

  ---------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------

  [CSS Transforms Module Level 2\
  [\#
  funcdef-translatez]](https://drafts.csswg.org/css-transforms-2/#funcdef-translatez)

  ---------------------------------------------------------------------------------------------

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

- [`transform`](transform.md)
- [`<transform-function>`](transform-function.md)
- [`translate`](_Resources/Markup%20And%20Styling/css/translate.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/translateZ>
