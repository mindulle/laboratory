\<alpha-value\>
===============

The `<alpha-value>`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [](css_types.md) represents a value that can be either a
[`<number>`](number.md) or a [`<percentage>`](percentage.md), specifying the
**[alpha
channel](https://developer.mozilla.org/en-US/docs/Glossary/Alpha)** or
**transparency** of a color.

Syntax
------

The value of an `<alpha-value>` is given as either a
[`<number>`](number.md) or a [`<percentage>`](percentage.md).

If given as a number, the useful range is 0 (fully transparent) to 1.0
(fully opaque), with decimal values in between; that is, 0.5 indicates
that half of the foreground color is used and half of the background
color is used. Values outside the range of 0 to 1 are permitted, but are
[clamped](https://en.wikipedia.org/wiki/Clamping_(graphics)) to lie
within the range 0 to 1.

If the alpha value is given as a percentage, 0% corresponds to fully
transparent while 100% indicates fully opaque.

Formal syntax
-------------

```
<alpha-value> = 
  <number>      |
  <percentage>  
```

Interpolation
-------------

When animated, values of the `<alpha-value>` CSS data type are
[interpolated](https://developer.mozilla.org/en-US/docs/Glossary/Interpolation)
as real, floating-point numbers. The speed of the interpolation is
determined by the [easing function](easing-function.md) associated with the
animation.

Examples
--------

### Setting text color opacity

The [`rgb()`](rgb.md) function accepts a fourth optional value
to specify an alpha value. The following example shows how to apply a
color with 60% opacity using the alpha value:

[css]

```css
/* <rgb()> */
color: rgb(34 12 64 / 60%);
```

### Setting shape image threshold

Here an alpha value is used to determine which parts of an image are
considered part of a shape:

[css]

```css
/* shape-image-threshold */
shape-image-threshold: 70%;
shape-image-threshold: 0.7;
```

Specifications
--------------

  ------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------

  [CSS Color Module Level 4\
  [\#
  type-def-alpha-value]](https://drafts.csswg.org/css-color/#type-def-alpha-value)

  ------------------------------------------------------------------------------------------

See also
--------

- [Fundamental text and font
    styling](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Fundamentals)
- [CSS data types](css_types.md)
- [CSS Color](css_colors.md)
- [`<color>`](color_value.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/alpha-value>
