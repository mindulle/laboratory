\<angle\>
=========

The `<angle>` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[data type](css_types.md) represents an angle value expressed in degrees,
gradians, radians, or turns. It is used, for example, in
[`<gradient>`](gradient.md)s and in some [`transform`](transform.md)
functions.

Try it
------

Syntax
------

The `<angle>` data type consists of a [`<number>`](number.md) followed by
one of the units listed below. As with all dimensions, there is no space
between the unit literal and the number. The angle unit is optional
after the number `0`.

Optionally, it may be preceded by a single `+` or `-` sign. Positive
numbers represent clockwise angles, while negative numbers represent
counterclockwise angles. For static properties of a given unit, any
angle can be represented by various equivalent values. For example,
`90deg` equals `-270deg`, and `1turn` equals `4turn`. For dynamic
properties, like when applying an [`animation`](animation.md) or
[`transition`](transition.md), the effect will nevertheless be different.

### Units

[`deg`](#deg)

:   Represents an angle in
    [degrees](https://en.wikipedia.org/wiki/Degree_%28angle%29). One
    full circle is `360deg`. Examples: `0deg`, `90deg`, `14.23deg`.

#### grad

:   Represents an angle in
    [gradians](https://en.wikipedia.org/wiki/Gradian). One full circle
    is `400grad`. Examples: `0grad`, `100grad`, `38.8grad`.

#### rad

:   Represents an angle in
    [radians](https://en.wikipedia.org/wiki/Radian). One full circle is
    2π radians which approximates to `6.2832rad`. `1rad` is 180/π
    degrees. Examples: `0rad`, `1.0708rad`, `6.2832rad`.

[`turn`](#turn)

:   Represents an angle in a number of turns. One full circle is
    `1turn`. Examples: `0turn`, `0.25turn`, `1.2turn`.

Examples
--------

### Setting a clockwise right angle

### Setting a flat angle

### Setting a counterclockwise right angle

### Setting a null angle

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Values and Units Module Level 4\
  [\# angles]](https://drafts.csswg.org/css-values/#angles)

  -----------------------------------------------------------------------

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

`angle`

2

12

3.6

9

15

4

2

18

4

14

3.2

1.0

`deg`

2

12

3.6

9

15

4

2

18

4

14

3.2

1.0

`grad`

2

12

3.6

9

15

4

2

18

4

14

3.2

1.0

`rad`

2

12

3.6

9

15

4

2

18

4

14

3.2

1.0

`turn`

2

12

13

9

15

4

2

18

14

14

3.2

1.0

See also
--------

- [CSS data types](css_types.md)
- The [`<gradient>`](gradient.md) type
- CSS rotation transforms: [`rotate()`](_Resources/Markup%20And%20Styling/css/transform-function/rotate.md),
    [`rotate3d()`](rotate3d.md),
    [`rotateX()`](rotatex.md),
    [`rotateY()`](rotatey.md), and
    [`rotateZ()`](rotatez.md)
- [CSS transforms](css_transforms.md)
- [Using CSS transforms](using_css_transforms.md)
- [Using CSS gradients](using_css_gradients.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/angle>
