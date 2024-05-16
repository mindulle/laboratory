CSS data types
==============

**CSS data types** define typical values (including keywords and units)
accepted by CSS properties and functions. They are a special kind of
[component value
type](https://www.w3.org/TR/css3-values/#component-types).

The most commonly-used types are defined in the [](css_values_and_units.md) specification. This specification also
defines [functional notations](css_functions.md), which allow for more
complex types or processing. Other types are defined in the
specifications to which they apply.

Below you will find a reference to the types that you are most likely to
come across, however it is not a comprehensive reference for all types
defined in every CSS specification.

Syntax
------

[css]

```css
selector {
  property: <unit-data-type>;
}
```

In formal CSS syntax, data types are denoted by a keyword placed between
the inequality signs \"`<`\" and \"`>`\".

Textual data types
------------------

These types include keywords and identifiers as well as strings, and
URLs.

[Pre-defined keywords](#pre-defined_keywords)

:   Keywords with a pre-defined meaning, for example, the value of
    `collapse` for the [`border-collapse`](border-collapse.md) property.

[CSS-wide keywords](#css-wide_keywords)

:   All properties, including custom properties, accept the CSS-wide
    keywords:

    [`initial`](initial)

    :   The value specified as the property\'s initial value.

    [`inherit`](inherit)

    :   The computed value of the property on the element\'s parent.

    [`revert`](revert)

    :   Rolls back the cascade to the value of the earlier origin.

    [`unset`](unset)

    :   Acts as `inherit` or `initial` depending on whether the property
        is inherited or not.

[`<custom-ident>`](custom-ident.md)

:   A user-defined identifier, for example the name assigned using the
    [`grid-area`](grid-area.md) property.

[`<dashed-ident>`](dashed-ident.md)

:   A `<custom-ident>` with the additional restriction that it must
    start with two dashes, for example, with [](using_css_custom_properties.md).

[`<string>`](string.md)

:   A quoted string, such as used for a value of the
    [`content`](content.md) property.

[`url()`](url.md)

:   A pointer to a resource, for example as the value of
    [`background-image`](background-image.md).

Numeric data types
------------------

These data types are used to indicate quantities, indexes, and
positions. The majority of these are defined in the Values and Units
specification, however additional types are described in other
specifications where they are specific to that specification alone ---
for example the `fr` unit in [CSS Grid
Layout](https://www.w3.org/TR/css-grid-1/#fr-unit).

[`<integer>`](integer.md)

:   One or more decimal units 0 through 9.

[`<number>`](number.md)

:   Real numbers which may also have a fractional component, for example
    1 or 1.34.

[`<dimension>`](dimension.md)

:   A number with a unit attached to it, for example 23px or 15em.

[`<percentage>`](percentage.md)

:   A number with a percentage sign attached to it, for example 10%.

[`<ratio>`](ratio.md)

:   A ratio, written with the syntax `<number> / <number>`.

[`<flex>`](flex_value.md)

:   A flexible length introduced for [CSS Grid Layout](css_grid_layout.md),
    written as a `<number>` with the `fr` unit attached and used for
    grid track sizing.

Quantities
----------

These types are used to specify distance and other quantities.

[`<length>`](length.md)

:   Lengths are a `<dimension>` and refer to distances.

[`<angle>`](angle.md)

:   Angles are used in properties such as
    [`linear-gradient()`](linear-gradient.md) and are a
    `<dimension>` with one of `deg`, `grad`, `rad`, or `turn` units
    attached.

[`<time>`](time.md)

:   Duration units are a `<dimension>` with an `s` or `ms` unit.

[`<frequency>`](frequency.md)

:   Frequencies are a `<dimension>` with a `Hz` or `kHz` unit attached.

[`<resolution>`](_Resources/Markup%20And%20Styling/css/resolution.md)

:   Is a `<dimension>` with a unit identifier of `dpi`, `dpcm`, `dppx`,
    or `x`.

Combinations of types
---------------------

Some CSS properties can take a dimension or a percentage value. In this
case the percentage value will be resolved to a quantity that matches
the allowable dimension. Properties which can accept a percentage in
addition to a dimension will use one of the types listed below.

[`<length-percentage>`](length-percentage.md)

:   A type that can accept a length or a percentage as a value.

[`<frequency-percentage>`](frequency-percentage.md)

:   A type that can accept a frequency or a percentage as a value.

[`<angle-percentage>`](angle-percentage.md)

:   A type that can accept an angle or a percentage as a value.

[`<time-percentage>`](time-percentage.md)

:   A type that can accept a time or a percentage as a value.

Color
-----

[The CSS Color Specification](https://www.w3.org/TR/css-color-4/)
defines the [`<color>`](color_value.md) data type, and other types which
relate to color in CSS.

[`<color>`](color_value.md)

:   Specified as a keyword or a numerical color value.

[`<alpha-value>`](alpha-value.md)

:   Specifies the transparency of a color. May be a `<number>`, in which
    case 0 is fully transparent and 1 is fully opaque, or a
    `<percentage>`, in which case 0% is fully transparent and 100% fully
    opaque.

[`<hue>`](hue.md)

:   Specifies the `<angle>`, with a unit identifier of `deg`, `grad`,
    `rad`, or `turn`, or unitless `<number>` interpreted as `deg`, of
    the [color
    wheel](https://developer.mozilla.org/en-US/docs/Glossary/Color_wheel)
    specific to the `<absolute-color-functions>` of which it is a
    component.

Images
------

[The CSS Images Specification](https://www.w3.org/TR/css-images-3/)
defines the data types which deal with images, including gradients.

[`<image>`](_Resources/Markup%20And%20Styling/css/image.md)

:   A URL reference to an image or a color gradient.

[`<color-stop-list>`]

:   A list of two or more color stops with optional transition
    information using a color hint.

[`<linear-color-stop>`]

:   A `<color>` and a `<length-percentage>` to indicate the color stop
    for this part of the gradient.

[`<linear-color-hint>`]

:   A `<length-percentage>` to indicate how the color interpolates.

[`<ending-shape>`]

:   Used for radial gradients; can have a keyword value of `circle` or
    `ellipse`.

[`<size>`]

:   Determines the size of the radial gradient\'s ending shape. This
    accepts a value of a keyword or a `<length>` but not a percentage.

2D positioning
--------------

The [`<position>`](position_value.md) data type is interpreted as defined
for the [`<background-position>`](background-position.md) property.

[`<position>`](position_value.md)

:   Defines the position of an object area. Accepts a keyword value such
    as `top` or `left`, or a `<length-percentage>`.

Calculation data types
----------------------

These data types are used in [](css_functions.md#math_functions) calculations.

[`<calc-sum>`](calc-sum.md)

:   A calculation which is a sequence of calculation values interspersed
    with addition (`+`) and subtraction (`-`) operators. This data type
    requires both values to have units.

[`<calc-product>`]

:   A calculation which is a sequence of calculation values interspersed
    with multiplication (`*`) and division (`/`) operators. When
    multiplying, one value must be unitless. When dividing, the second
    value must be unitless.

[`<calc-value>`]

:   Defines accepted values for calculations, values such as
    [`<number>`](number.md), [`<dimension>`](dimension.md),
    [`<percentage>`](percentage.md), [`<calc-constant>`](calc-constant.md) or
    nested [`<calc-sum>`](calc-sum.md) calculations.

[`<calc-constant>`](calc-constant.md)

:   Defines a number of CSS keywords representing numeric constants such
    as `e` and `π`, that can be used in CSS math functions.

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Values and Units Module Level 4\
  ](https://drafts.csswg.org/css-values/)

  -----------------------------------------------------------------------

See also
--------

- [CSS Units and Values](css_values_and_units.md)
- [Introduction to CSS: Values and
    Units](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units)
- [CSS Functional Notation](css_functions.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Types>
