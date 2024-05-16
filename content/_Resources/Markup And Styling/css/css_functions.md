CSS value functions
===================

**CSS value functions** are statements that invoke special data
processing or calculations to return a
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[value](css_values_and_units.md) for a CSS property. CSS value functions
represent more complex [data types](css_types.md) and they may take some
input arguments to calculate the return value.

Syntax
------

[css]

```css
selector {
  property: function([argument]? [, argument]!);
}
```

The value syntax starts with the **name of the function**, followed by a
left parenthesis `(`. Next up are the argument(s), and the function is
finished off with a closing parenthesis `)`.

Functions can take multiple arguments, which are formatted similarly to
CSS property values. Whitespace is allowed, but they are optional inside
the parentheses. In some functional notations multiple arguments are
separated by commas, while others use spaces.

**Note:** The CSS value functions are used as property values and should
not be confused with pseudo-classes. The [](pseudo-classes.md#functional_pseudo-classes), [](pseudo-classes.md#linguistic_pseudo-classes), and several
[](pseudo-classes.md#tree-structural_pseudo-classes) require
parameter values, but they\'re not value functions. The [](at-rule.md#conditional_group_rules) are also not value functions;
the parentheses are used for groupings.

Transform functions
-------------------

The [`<transform-function>`](transform-function.md) CSS [](css_types.md) represent appearance transformation. It is used as a
value of [`transform`](transform.md) property.

### Translate functions

[`translateX()`](translatex.md)

:   Translates an element horizontally.

[`translateY()`](translatey.md)

:   Translates an element vertically.

[`translateZ()`](translatez.md)

:   Translates an element along the z-axis.

[`translate()`](_Resources/Markup%20And%20Styling/css/transform-function/translate.md)

:   Translates an element on the 2D plane.

[`translate3d()`](translate3d.md)

:   Translates an element in 3D space.

### Rotation functions

[`rotateX()`](rotatex.md)

:   Rotates an element around the horizontal axis.

[`rotateY()`](rotatey.md)

:   Rotates an element around the vertical axis.

[`rotateZ()`](rotatez.md)

:   Rotates an element around the z-axis.

[`rotate()`](_Resources/Markup%20And%20Styling/css/transform-function/rotate.md)

:   Rotates an element around a fixed point on the 2D plane.

[`rotate3d()`](rotate3d.md)

:   Rotates an element around a fixed axis in 3D space.

### Scaling functions

[`scaleX()`](scalex.md)

:   Scales an element up or down horizontally.

[`scaleY()`](scaley.md)

:   Scales an element up or down vertically.

[`scaleZ()`](scalez.md)

:   Scales an element up or down along the z-axis.

[`scale()`](_Resources/Markup%20And%20Styling/css/transform-function/scale.md)

:   Scales an element up or down on the 2D plane.

[`scale3d()`](scale3d.md)

:   Scales an element up or down in 3D space.

### Skew functions

[`skewX()`](skewx.md)

:   Skews an element in the horizontal direction.

[`skewY()`](skewy.md)

:   Skews an element in the vertical direction.

[`skew()`](skew.md)

:   Skews an element on the 2D plane.

### Matrix functions

[`matrix()`](matrix.md)

:   Describes a homogeneous 2D transformation matrix.

[`matrix3d()`](matrix3d.md)

:   Describes a 3D transformation as a 4×4 homogeneous matrix.

### Perspective functions

[`perspective()`](_Resources/Markup%20And%20Styling/css/transform-function/perspective.md)

:   Sets the distance between the user and the z=0 plane.

Math functions
--------------

The math functions allow CSS numeric values to be written as
mathematical expressions.

### Basic arithmetic

[`calc()`](calc.md)

:   Performs basic arithmetic calculations on numerical values.

### Comparison functions

[`min()`](min.md)

:   Calculates the smallest of a list of values.

[`max()`](max.md)

:   Calculates the largest of a list of values.

[`clamp()`](clamp.md)

:   Calculates the central of a minimum, central, and maximum values.

### Stepped value functions

[`round()`](round.md)

:   Calculates a rounded number based on a rounding strategy.

[`mod()`](mod.md)

:   Calculates a modulus (with the same sign as the divisor) when
    dividing one number by another.

[`rem()`](rem.md)

:   Calculates a remainder (with the same sign as the dividend) when
    dividing one number by another.

### Trigonometric functions

[`sin()`](sin.md)

:   Calculates the trigonometric sine of a number.

[`cos()`](cos.md)

:   Calculates the trigonometric cosine of a number.

[`tan()`](tan.md)

:   Calculates the trigonometric tangent of a number.

[`asin()`](asin.md)

:   Calculates the trigonometric inverse sine of a number.

[`acos()`](acos.md)

:   Calculates the trigonometric inverse cosine of a number.

[`atan()`](atan.md)

:   Calculates the trigonometric inverse tangent of a number.

[`atan2()`](atan2.md)

:   Calculates the trigonometric inverse tangent of two-numbers in a
    plane.

### Exponential functions

[`pow()`](pow.md)

:   Calculates the base raised to the power of a number.

[`sqrt()`](sqrt.md)

:   Calculates the square root of a number.

[`hypot()`](hypot.md)

:   Calculates the square root of the sum of the squares of its
    arguments.

[`log()`](log.md)

:   Calculates the logarithm of a number.

[`exp()`](exp.md)

:   Calculates `e` raised to the power of a number.

### Sign-related functions

[`abs()`](abs.md)

:   Calculates the absolute value of a number.

[`sign()`](sign.md)

:   Calculates the sign (positive or negative) of the number.

Filter functions
----------------

The [`<filter-function>`](filter-function.md) CSS [data type](css_types.md)
represents a graphical effect that can change the appearance of an input
image. It is used in the [`filter`](filter.md) and
[`backdrop-filter`](backdrop-filter.md) properties.

[`blur()`](blur.md)

:   Increases the image gaussian blur.

[`brightness()`](brightness.md)

:   Brightens or darkens an image.

[`contrast()`](contrast.md)

:   Increases or decreases the image contrast.

[`drop-shadow()`](drop-shadow.md)

:   Applies a drop shadow behind an image.

[`grayscale()`](grayscale.md)

:   Converts an image to grayscale.

[`hue-rotate()`](hue-rotate.md)

:   Changes the overall hue of an image.

[`invert()`](invert.md)

:   Inverts the colors of an image.

[`opacity()`](_Resources/Markup%20And%20Styling/css/filter-function/opacity.md)

:   Adds transparency to an image.

[`saturate()`](saturate.md)

:   Changes the overall saturation of an image.

[`sepia()`](sepia.md)

:   Increases the sepia of an image.

Color functions
---------------

The [`<color>`](color_value.md) CSS [data type](css_types.md) specifies
different color representations.

[`rgb()`](rgb.md)

:   Defines a given color according to its red, green, blue and alpha
    (transparency) components.

[`hsl()`](hsl.md)

:   Defines a given color according to its hue, saturation, lightness
    and alpha (transparency) components.

[`hwb()`](hwb.md)

:   Defines a given color according to its hue, whiteness and blackness
    components.

[`lch()`](lch.md)

:   Defines a given color according to its lightness, chroma and hue
    components.

[`oklch()`](oklch.md)

:   Defines a given color according to its lightness, chroma, hue and
    alpha (transparency) components.

[`lab()`](lab.md)

:   Defines a given color according to its lightness, a-axis distance
    and b-axis distance in the lab colorspace.

[`oklab()`](oklab.md)

:   Defines a given color according to its lightness, a-axis distance,
    b-axis distance in the lab colorspace and alpha (transparency).

[`color()`](_Resources/Markup%20And%20Styling/css/color_value/color.md)

:   Specifies a particular, specified colorspace rather than the
    implicit sRGB colorspace.

[`color-mix()`](color-mix.md)

:   Mixes two color values in a given colorspace by a given amount.

[`color-contrast()`](color-contrast.md) [Experimental]

:   Selects the highest color contrast from a list of colors, compare to
    a base color value.

[`device-cmyk()`](device-cmyk.md) [Experimental]

:   Defines CMYK colors in a device-independent way.

Image functions
---------------

The [`<image>`](_Resources/Markup%20And%20Styling/css/image.md) CSS [data type](css_types.md) provides graphical
representation of images or gradients.

### Gradient functions

[`linear-gradient()`](linear-gradient.md)

:   Linear gradients transition colors progressively along an imaginary
    line.

[`radial-gradient()`](radial-gradient.md)

:   Radial gradients transition colors progressively from a center point
    (origin).

[`conic-gradient()`](conic-gradient.md)

:   Conic gradients transition colors progressively around a circle.

[`repeating-linear-gradient()`](repeating-linear-gradient.md)

:   Is similar to `linear-gradient()` and takes the same arguments, but
    it repeats the color stops infinitely in all directions so as to
    cover its entire container.

[`repeating-radial-gradient()`](repeating-radial-gradient.md)

:   Is similar to `radial-gradient()` and takes the same arguments, but
    it repeats the color stops infinitely in all directions so as to
    cover its entire container.

[`repeating-conic-gradient()`](repeating-conic-gradient.md)

:   Is similar to `conic-gradient()` and takes the same arguments, but
    it repeats the color stops infinitely in all directions so as to
    cover its entire container.

### Image functions

[`image()`](_Resources/Markup%20And%20Styling/css/image/image.md) [Experimental]

:   Defines an [`<image>`](_Resources/Markup%20And%20Styling/css/image.md) in a similar fashion to the
    [`url()`](url.md) function, but with added functionality including
    specifying the image\'s directionality and fallback images for when
    the preferred image is not supported.

[`image-set()`](image-set.md)

:   Picks the most appropriate CSS image from a given set, primarily for
    high pixel density screens.

[`cross-fade()`](cross-fade.md)

:   Blends two or more images at a defined transparency.

[`element()`](element().md) [Experimental]

:   Defines an [`<image>`](_Resources/Markup%20And%20Styling/css/image.md) value generated from an arbitrary HTML
    element.

[`paint()`](paint.md)

:   Defines an [`<image>`](_Resources/Markup%20And%20Styling/css/image.md) value generated with a PaintWorklet.

Counter functions
-----------------

CSS counter functions are generally used with the [`content`](content.md)
property, although in theory, they may be used wherever a
[`<string>`](string.md) is supported.

[`counter()`](counter.md)

:   Returns a string representing the current value of the named counter
    if there is one.

[`counters()`](counters.md)

:   Enables nested counters, returning a concatenated string
    representing the current values of the named counters, if there are
    any.

[`symbols()`](symbols.md)

:   Defines the counter styles inline, directly as the value of a
    property.

Shape functions
---------------

The [`<basic-shape>`](basic-shape.md) CSS [data type](css_types.md) represents
a graphical shape. It is used in the [`clip-path`](clip-path.md),
[`offset-path`](offset-path.md), and [`shape-outside`](shape-outside.md)
properties.

[`circle()`](circle.md)

:   Defines a circle shape.

[`ellipse()`](ellipse.md)

:   Defines an ellipse shape.

[`inset()`](_Resources/Markup%20And%20Styling/css/basic-shape/inset.md)

:   Defines an inset rectangle shape.

[`polygon()`](polygon.md)

:   Defines a polygon shape.

[`path()`](path.md)

:   Accepts an SVG path string to enable a shape to be drawn.

Reference functions
-------------------

The following functions are used as a value of properties to reference a
value defined elsewhere.

[`attr()`](attr.md)

:   Uses the attributes defined on HTML element.

[`env()`](env.md)

:   Uses the user-agent defined as environment variable.

[`url()`](url.md)

:   Uses a file from the specified URL.

[`var()`](var().md)

:   Uses the custom property value instead of any part of a value of
    another property.

Grid functions
--------------

The following functions are used to define a [](css_grid_layout.md).

[`fit-content()`](fit-content.md)

:   Clamps a given size to an available size according to the formula
    `min(maximum size, max(minimum size, argument))`.

[`minmax()`](minmax.md)

:   Defines a size range greater-than or equal-to *min* and less-than or
    equal-to *max*.

[`repeat()`](repeat.md)

:   Represents a repeated fragment of the track list, allowing a large
    number of columns or rows that exhibit a recurring pattern.

Font functions
--------------

CSS font functions are used with the
[`font-variant-alternates`](font-variant-alternates.md) property to control
the use of alternate glyphs.

[`stylistic()`](font-variant-alternates.md#stylistic)

:   Enables stylistic alternates for individual characters. The
    parameter is a font-specific name mapped to a number. It corresponds
    to the OpenType value `salt`, like `salt 2`.

[`styleset()`](font-variant-alternates.md#styleset)

:   Enables stylistic alternatives for sets of characters. The parameter
    is a font-specific name mapped to a number. It corresponds to the
    OpenType value `ssXY`, such as `ss02`.

[`character-variant()`](font-variant-alternates.md#character-variant)

:   Enables specific stylistic alternatives for characters. It is
    similar to `styleset()`, but doesn\'t create coherent glyphs for a
    set of characters; individual characters will have independent and
    not necessarily coherent styles. The parameter is a font-specific
    name mapped to a number. It corresponds to the OpenType value
    `cvXY`, such as `cv02`.

[`swash()`](font-variant-alternates.md#swash)

:   Enables
    [swash](https://en.wikipedia.org/wiki/Swash_%28typography%29)
    glyphs. The parameter is a font-specific name mapped to a number. It
    corresponds to the OpenType values `swsh` and `cswh`, such as
    `swsh 2` and `cswh 2`.

[`ornaments()`](font-variant-alternates.md#ornaments)

:   Enables ornaments such as
    [fleurons](https://en.wikipedia.org/wiki/Fleuron_%28typography%29)
    and other dingbat glyphs. The parameter is a font-specific name
    mapped to a number. It corresponds to the OpenType value `ornm`,
    such as `ornm 2`.

[`annotation()`](font-variant-alternates.md#annotation)

:   Enables annotations such as circled digits or inverted characters.
    The parameter is a font-specific name mapped to a number. It
    corresponds to the OpenType value `nalt`, such as `nalt 2`.

Easing functions
----------------

The following functions are used as a value in transition and animation
properties.

[`linear()`](easing-function.md#linear_easing_function)

:   Easing function that interpolates linearly between its points.

[`cubic-bezier()`](easing-function.md#cubic_bézier_easing_function)

:   Easing function that defines a cubic Bézier curve.

[`steps()`](easing-function.md#step_easing_function)

:   Iteration along a specified number of stops along the transition,
    displaying each stop for equal lengths of time.

Animation functions
-------------------

The following functions are used as a value of different
`animation-timeline` properties. See
[`animation-timeline`](animation-timeline.md) for more details about these.

[`scroll()`](scroll.md)

:   Sets the [`animation-timeline`](animation-timeline.md) of an element to
    an *anonymous scroll progress timeline*.

[`view()`](view.md)

:   Sets the [`animation-timeline`](animation-timeline.md) of an element to
    an *anonymous view progress timeline*.

See also
--------

- [CSS Values and Units](css_values_and_units.md)
- [Introduction to CSS: Values and
    Units](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Functions>
