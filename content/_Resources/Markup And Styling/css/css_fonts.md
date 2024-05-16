CSS fonts
=========

The **CSS fonts** module defines font-related properties and how font
resources are loaded. It lets you define the style of a font, such as
its family, size and weight, and the glyph variants to use when multiple
are available for a single character.

A font is a resource file containing the visual representation of
characters, mapping character codes to glyphs that represent letters,
numbers, punctuation and even emojis of a typeface. A font family is a
group of fonts that share common design styles and font properties, with
each member of the group providing different ways of displaying the
glyphs, varying by stroke weight, slant, or relative width, among other
attributes. A font typically represents a single style of a typeface,
such as Helvetica that is Bold and Italic. A font family is the complete
set of styles. Including such a font in a document or design is done by
defining a separate `@font-face` declaration for each font resource.

The properties, at-rules, and descriptors of the CSS fonts module enable
the downloading of multiple variations of a font. They also define the
font file to use for a particular font characteristic, along with
fallback instructions in case a resource fails to load. The CSS font
selection mechanism describes the process of matching a given set of CSS
font properties to a single font face.

The CSS fonts module also supports variable fonts. Unlike regular fonts,
where each style is implemented as a separate font file, variable fonts
can contain all styles within a single file. By using a single
`@font-face` declaration, you can import a variable font that includes
all the styles. Depending on the font, this can include a multitude of
font variants. Variable fonts are a part of the OpenType font
specification.

Reference
---------

### Properties

- [`font`](font.md) shorthand
- [`font-family`](_Resources/Markup%20And%20Styling/css/font-family.md)
- [`font-feature-settings`](_Resources/Markup%20And%20Styling/css/font-feature-settings.md)
- [`font-kerning`](font-kerning.md)
- [`font-language-override`](font-language-override.md)
- [`font-optical-sizing`](font-optical-sizing.md)
- [`font-palette`](font-palette.md)
- [`font-size`](font-size.md)
- [`font-size-adjust`](font-size-adjust.md)
- [`font-stretch`](_Resources/Markup%20And%20Styling/css/font-stretch.md)
- [`font-style`](_Resources/Markup%20And%20Styling/css/font-style.md)
- [`font-weight`](_Resources/Markup%20And%20Styling/css/font-weight.md)
- [`font-synthesis`](font-synthesis.md) shorthand
- [`font-synthesis-small-caps`](font-synthesis-small-caps.md)
- [`font-synthesis-style`](font-synthesis-style.md)
- [`font-synthesis-weight`](font-synthesis-weight.md)
- [`font-variant`](font-variant.md) shorthand
- [`font-variant-alternates`](font-variant-alternates.md)
- [`font-variant-caps`](font-variant-caps.md)
- [`font-variant-east-asian`](font-variant-east-asian.md)
- [`font-variant-emoji`](font-variant-emoji.md)
- [`font-variant-ligatures`](font-variant-ligatures.md)
- [`font-variant-numeric`](font-variant-numeric.md)
- [`font-variant-position`](font-variant-position.md)
- [`font-variation-settings`](_Resources/Markup%20And%20Styling/css/font-variation-settings.md)

### At-rules and descriptors

[At-rule:](#at-rule) [`@font-face`](@font-face.md)

:   Descriptors:

    -   [`ascent-override`](@font-face/ascent-override)
    -   [`descent-override`](@font-face/descent-override)
    -   [`font-display`](@font-face/font-display)
    -   [`font-family`](@font-face/font-family)
    -   [`font-feature-settings`](@font-face/font-feature-settings)
    -   [`font-language-override`]
    -   [`font-named-instance`]
    -   [`font-stretch`](@font-face/font-stretch)
    -   [`font-style`](@font-face/font-style)
    -   [`font-variation-settings`](@font-face/font-variation-settings)
    -   [`font-weight`](@font-face/font-weight)
    -   [`line-gap-override`](@font-face/line-gap-override)
    -   [`size-adjust`](@font-face/size-adjust)
    -   [`src`](@font-face/src)
    -   [`unicode-range`](@font-face/unicode-range)

[At-rule:](#at-rule_2) [`@font-feature-values`](@font-feature-values.md)

:   Descriptor:

    -   [`font-display`](@font-feature-values/font-display)

[At-rule:](#at-rule_3) [`@font-palette-values`](@font-palette-values.md)

:   Descriptors:

    -   [`base-palette`](@font-palette-values/base-palette)
    -   [`font-family`](@font-palette-values/font-family)
    -   [`override-colors`](@font-palette-values/override-colors)

### Data types

`font-size` types:

- [`<absolute-size>`](absolute-size.md)
- [`<relative-size>`](relative-size.md)

`font-family` type:

- [`<generic-family>`](generic-family.md)

`font-feature-settings` type:

- [`<feature-tag-value>`](_Resources/Markup%20And%20Styling/css/font-feature-settings.md#values)

`font-format` type:

- [`<font-format>`](@supports.md#font-format)

`font-stretch` type:

- [`<font-stretch-css3>`](_Resources/Markup%20And%20Styling/css/font-stretch.md#values)

`font-tech` types:

- [`<color-font-tech>`](@supports.md#font-tech)
- [`<font-features-tech>`](@supports.md#font-tech)
- [`<font-tech>`](@supports.md#font-tech)

`font-variant` types:

- [`<font-variant-css2>`](font-variant.md)
- [`<east-asian-variant-values>`](font-variant.md#values)
- [`<east-asian-width-values>`](font-variant.md#values)

`font-variant-ligatures` types:

- [`<common-lig-values>`](font-variant-ligatures.md#values)
- [`<contextual-alt-values>`](font-variant-ligatures.md#values)
- [`<discretionary-lig-values>`](font-variant-ligatures.md#values)
- [`<historical-lig-values>`](font-variant-ligatures.md#values)

`font-variant-numeric` types:

- [`<numeric-figure-values>`](font-variant-numeric.md#values)
- [`<numeric-fraction-values>`](font-variant-numeric.md#values)
- [`<numeric-spacing-values>`](font-variant-numeric.md#values)

`font-weight` type:

- [`<font-weight-absolute>`](_Resources/Markup%20And%20Styling/css/font-weight.md#values)

### Interfaces

- [`CSSFontFaceRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSFontFaceRule)
- [`CSSFontFeatureValuesRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSFontFeatureValuesRule)
- [`CSSFontPaletteValuesRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSFontPaletteValuesRule)

Guides
------

[Learn: Fundamental text and font styling](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Fundamentals)

:   This beginner\'s learning article covers the basic fundamentals of
    text and font styling. It covers how to set the font weight, family,
    and style by using the [`font`](font.md) shorthand and how to align
    text and manage line and letter spacing.

[Learn: Web fonts](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Web_fonts)

:   This beginner\'s learning article explains how to use custom fonts
    on your web page to allow for more varied and custom text styling.

[OpenType font features guide](opentype_fonts_guide.md)

:   Font features or variants refer to different glyphs or character
    styles contained within an OpenType font. These include things like
    ligatures (special glyphs that combine characters like \'fi\' or
    \'ffl\'), kerning (adjustments to the spacing between specific
    letterform pairings), fractions, numeral styles, and a number of
    others. These are all referred to as OpenType Features, and are made
    available to use on the web via specific properties and a low-level
    control property ---
    [`font-feature-settings`](_Resources/Markup%20And%20Styling/css/font-feature-settings.md). This article
    provides you with all you need to know about using OpenType font
    features in CSS.

[Variable fonts guide](variable_fonts_guide.md)

:   This article will help you get started with using variable fonts.

[Improving font perfomance](https://developer.mozilla.org/en-US/docs/Learn/Performance/CSS#improving_font_performance)

:   This article, part of the CSS performance guide, discusses font
    loading, loading only the required glyphs, and defining font display
    behavior with the `font-display` descriptor.

Related concepts
----------------

- [`letter-spacing`](letter-spacing.md) CSS property
- [`line-height`](line-height.md) CSS property
- [`text-transform`](text-transform.md) CSS property

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Fonts Module Level 4\
  ](https://drafts.csswg.org/css-fonts/)

  -----------------------------------------------------------------------

See also
--------

- [CSS font loading](css_font_loading.md) module
- [CSS font loading
    API](https://developer.mozilla.org/en-US/docs/Web/API/CSS_Font_Loading_API)
- [CSS text](css_text.md) module
- [CSS writing modes](css_writing_modes.md) module

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_fonts>
