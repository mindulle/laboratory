ellipse()
=========

The `ellipse()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
function is one of the [`<basic-shape>`](basic-shape.md) [](css_types.md).

Try it
------

Syntax
------

[css]

```css
shape-outside: ellipse(40% 50% at left);
shape-outside: ellipse(closest-side farthest-side at 30%);
```

An ellipse is essentially a squashed circle and so `ellipse()` acts in a
very similar way to [`circle()`](circle.md) except that we have to specify
two radii x and y.

### Values

[`<shape-radius>`](#shape-radius)

:   Two radii, x and y in that order. These may be a
    [`<length>`](length.md), or a [`<percentage>`](percentage.md) or
    values `closest-side` and `farthest-side`.

    [`closest-side`](#closest-side)

    :   Uses the length from the center of the shape to the closest side
        of the reference box. For ellipses, this is the closest side in
        the radius dimension.

    [`farthest-side`](#farthest-side)

    :   Uses the length from the center of the shape to the farthest
        side of the reference box. For ellipses, this is the farthest
        side in the radius dimension.

[`<position>`](#position)

:   Moves the center of the ellipse. May be a [`<length>`](length.md),
    or a [`<percentage>`](percentage.md), or a values such as `left`.
    The `<position>` value defaults to center if omitted.

Examples
--------

### Basic ellipse() example

This example shows an ellipse with an x radius of 40%, a y radius of 50%
and the position being left. This means that the center of the ellipse
is on the left edge of the box giving us a half ellipse shape to wrap
our text around. You can change these values to see how the ellipse
changes.

### Using closest-side / farthest-side values

The keyword values of `closest-side` and `farthest-side` are useful to
create a quick ellipse based on the size of the floated element
reference box.

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------

  [CSS Shapes Module Level 1\
  [\#
  funcdef-basic-shape-ellipse]](https://drafts.csswg.org/css-shapes/#funcdef-basic-shape-ellipse)

  ---------------------------------------------------------------------------------------------------------

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

`ellipse`

37

79

54

No

24

10.1

37

37

54

24

10.3

3.0

See also
--------

- Properties that use this data type: [`clip-path`](clip-path.md),
    [`shape-outside`](shape-outside.md)
- [Guide to Basic Shapes](basic_shapes.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/basic-shape/ellipse>
