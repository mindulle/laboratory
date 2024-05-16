inset()
=======

The `inset()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
function defines a rectangle at the specified inset distances from each
side of the reference box. It is a basic shape function used to define
one of the [`<basic-shape>`](basic-shape.md) [data types](css_types.md).

Try it
------

Syntax
------

[css]

```css
shape-outside: inset(20px 50px 10px 0 round 50px);
```

### Values

[`<length-percentage>`](#length-percentage14)

:   When all of the four arguments are supplied they represent the top,
    right, bottom and left offsets from the reference box inward that
    define the positions of the edges of the inset rectangle. These
    arguments follow the syntax of the margin shorthand, that let you
    set all four insets with one, two or four values.

[`<border-radius>`](#border-radius)

:   The optional [`<border-radius>`](border-radius.md) argument(s)
    define rounded corners for the inset rectangle using the
    border-radius shorthand syntax.

Examples
--------

### Basic inset example

In the example below we have an `inset()` shape used to pull content
over the floated element. Change the offset values to see how the shape
changes.

Specifications
--------------

  -----------------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------------

  [CSS Shapes Module Level 1\
  [\#
  funcdef-basic-shape-inset]](https://drafts.csswg.org/css-shapes/#funcdef-basic-shape-inset)

  -----------------------------------------------------------------------------------------------------

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

`inset`

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
- [CSS shapes](css_shapes.md) module
- [Guide to basic shapes](basic_shapes.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/basic-shape/inset>
