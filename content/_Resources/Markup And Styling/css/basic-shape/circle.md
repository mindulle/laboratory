circle()
========

The `circle()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
function is one of the [`<basic-shape>`](basic-shape.md) [](css_types.md).

Try it
------

Syntax
------

[css]

```css
shape-outside: circle(50%);
clip-path: circle(6rem at 12rem 8rem);
```

### Values

[`<shape-radius>`](#shape-radius)

:   This may be a [`<length>`](length.md), or a
    [`<percentage>`](percentage.md) or values `closest-side` and
    `farthest-side`.

    [`closest-side`](#closest-side)

    :   Uses the length from the center of the shape to the closest side
        of the reference box. For circles, this is the closest side in
        any dimension.

    [`farthest-side`](#farthest-side)

    :   Uses the length from the center of the shape to the farthest
        side of the reference box. For circles, this is the closest side
        in any dimension.

[`<position>`](#position)

:   Moves the center of the circle. May be a [`<length>`](length.md), or
    a [`<percentage>`](percentage.md), or a values such as `left`. The
    `<position>` value defaults to center if omitted.

Examples
--------

### Basic circle

In the example below, the [`shape-outside`](shape-outside.md) property
has a value of `circle(50%)`, which defines a circle on a floated
element for the text to flow round.

Specifications
--------------

  -------------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------------

  [CSS Shapes Module Level 1\
  [\#
  funcdef-basic-shape-circle]](https://drafts.csswg.org/css-shapes/#funcdef-basic-shape-circle)

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

`circle`

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
https://developer.mozilla.org/en-US/docs/Web/CSS/basic-shape/circle>
