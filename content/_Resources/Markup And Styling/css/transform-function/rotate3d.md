rotate3d()
==========

The `rotate3d()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) defines a transformation that rotates an
element around a fixed axis in 3D space, without deforming it. Its
result is a [`<transform-function>`](transform-function.md) data type.

Try it
------

In 3D space, rotations have three degrees of freedom, which together
describe a single axis of rotation. The axis of rotation is defined by
an \[x, y, z\] vector and pass by the origin (as defined by the
[`transform-origin`](transform-origin.md) property). If, as specified,
the vector is not *normalized* (i.e., if the sum of the square of its
three coordinates is not 1), the [user
agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent)
will normalize it internally. A non-normalizable vector, such as the
null vector, \[0, 0, 0\], will cause the rotation to be ignored, but
without invalidating the whole CSS property.

**Note:** Unlike rotations in the 2D plane, the composition of 3D
rotations is usually not commutative. In other words, the order in which
the rotations are applied impacts the result.

Syntax
------

The amount of rotation created by `rotate3d()` is specified by three
[`<number>`](number.md)s and one [`<angle>`](angle.md). The `<number>`s
represent the x-, y-, and z-coordinates of the vector denoting the axis
of rotation. The `<angle>` represents the angle of rotation; if
positive, the movement will be clockwise; if negative, it will be
counter-clockwise.

[css]

```css
rotate3d(x, y, z, a)
```

### Values

[`x`](#x)

:   Is a [`<number>`](number.md) describing the x-coordinate of the
    vector denoting the axis of rotation which can be a positive or
    negative number.

[`y`](#y)

:   Is a [`<number>`](number.md) describing the y-coordinate of the
    vector denoting the axis of rotation which can be a positive or
    negative number.

[`z`](#z)

:   Is a [`<number>`](number.md) describing the z-coordinate of the
    vector denoting the axis of rotation which can be a positive or
    negative number.

[`a`](#a)

:   Is an [`<angle>`](angle.md) representing the angle of the rotation.
    A positive angle denotes a clockwise rotation, a negative angle a
    counter-clockwise one.

![](data:image/png;base64,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)

Examples
--------

### Rotating on the y-axis

#### HTML

[html]

```html
<div>Normal</div>
<div class="rotated">Rotated</div>
```

#### CSS

[css]

```css
body {
  perspective: 800px;
}

div {
  width: 80px;
  height: 80px;
  background-color: skyblue;
}

.rotated {
  transform: rotate3d(0, 1, 0, 60deg);
  background-color: pink;
}
```

#### Result

### Rotating on a custom axis

#### HTML

[html]

```html
<div>Normal</div>
<div class="rotated">Rotated</div>
```

#### CSS

[css]

```css
body {
  perspective: 800px;
}

div {
  width: 80px;
  height: 80px;
  background-color: skyblue;
}

.rotated {
  transform: rotate3d(1, 2, -1, 192deg);
  background-color: pink;
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
  funcdef-rotate3d]](https://drafts.csswg.org/css-transforms-2/#funcdef-rotate3d)

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

See also
--------

- [`transform`](transform.md) property
- [`rotate`](_Resources/Markup%20And%20Styling/css/rotate.md) property
- [`<transform-function>`](transform-function.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/rotate3d>
