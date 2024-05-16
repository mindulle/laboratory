CSS colors
==========

The **CSS colors** module defines colors, color types, color blending,
opacity, and how you can apply these colors and effects to HTML content.

While this module has only two CSS properties, [`color`](_Resources/Markup%20And%20Styling/css/color.md) and
[`opacity`](_Resources/Markup%20And%20Styling/css/opacity.md), over 20 CSS and SVG properties, CSS images,
at-rules, and \@media rules depend on these two properties.

### Colors in action

The color syntax converter below shows the values of the currently
selected color in [red-green-blue](rgb.md) (RGB),
[hexadecimal](hex-color.md) (HEX), [](hsl.md) (HSL), and [](hwb.md) (HWB) CSS color formats. All the RGB, HEX,
HSL, and HWB color values here, while written differently, represent the
same color value.

Selecting a color via the [color
picker](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/color)
and an opacity via the
[slider](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/range)
updates the RGB, HEX, HSL, and HWB values. When you choose a new color
or opacity value, the color of the background and the slider update via
the CSS properties [`background-color`](background-color.md) and
[`accent-color`](accent-color.md), respectively.

To see the code for this color syntax converter, [view the source on
GitHub](https://github.com/mdn/css-examples/blob/main/modules/colors.html).

Reference
---------

### Properties

- [`color`](_Resources/Markup%20And%20Styling/css/color.md)
- [`opacity`](_Resources/Markup%20And%20Styling/css/opacity.md)

### At-rules and descriptors

- [`@color-profile`](@color-profile.md)
  - [`components`](@color-profile.md#descriptors) descriptor
  - [`rendering-intent`](@color-profile.md#descriptors) descriptor
  - [`src`](@color-profile.md#descriptors) descriptor

### Functions

- Absolute color functions, including:
  - [`rgb()`](rgb.md) and its `rgba()` alias
  - [`hsl()`](hsl.md) and its `hsla()` alias
  - [`hwb()`](hwb.md)
  - [`lab()`](lab.md)
  - [`lch()`](lch.md)
  - [`oklab()`](oklab.md)
  - [`oklch()`](oklch.md)
  - [`color()`](_Resources/Markup%20And%20Styling/css/color_value/color.md)
- [`color-contrast()`](color-contrast.md)
    [Experimental]
- [`color-mix()`](color-mix.md)
- [`device-cmyk()`](device-cmyk.md)
    [Experimental]

### Data types

- [`<color>`](color_value.md)
- [`<absolute-color-function>`](#functions)
- [`<hex-color>`](hex-color.md)
- [`<named-color>`](named-color.md)
- [`<alpha-value>`](alpha-value.md)
- [`<hue>`](hue.md)
- [`<system-color>`](system-color.md)
- [`<colorspace-params>`](_Resources/Markup%20And%20Styling/css/color_value/color.md#using_predefined_colorspaces_with_color)

### Keywords

- [`currentcolor`](color_value.md#currentcolor_keyword)
- [`transparent`](named-color.md#transparent)

### Interfaces

- `CSSColorProfileRule` [Experimental]

Guides
------

[Applying color to HTML elements using CSS](applying_color.md)

:   A guide to using CSS to apply color to a variety of types of
    content. All color-related CSS properties are touched upon.

[Understanding color and luminance](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_Colors_and_Luminance)

:   Color perception and using colors with color insensitive (color
    blind) users, reduced vision users and users with vestibular
    disorders or other neurological disorders in mind.

[WCAG 1.4.1: Color contrast](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable/Color_contrast)

:   Explanation of contrast requirements between background and
    foreground content to ensure legibility.

[Color picker tool](color_picker_tool.md)

:   This tool makes it easy to create, adjust, and experiment with
    custom colors.

Related concepts
----------------

- CSS properties that are part of other specifications:
  - [`accent-color`](accent-color.md)
  - [`background-color`](background-color.md)
  - [`background-image`](background-image.md)
  - [`border-color`](border-color.md)
  - [`box-shadow`](box-shadow.md)
  - [`caret-color`](caret-color.md)
  - [`color`](_Resources/Markup%20And%20Styling/css/color.md)
  - [`color-scheme`](color-scheme.md)
  - [`column-rule-color`](column-rule-color.md)
  - [`outline-color`](outline-color.md)
  - [`scrollbar-color`](scrollbar-color.md)
  - [`text-decoration-color`](text-decoration-color.md)
  - [`text-emphasis-color`](text-emphasis-color.md)
  - [`text-shadow`](text-shadow.md)
  - [`-webkit-tap-highlight-color`](-webkit-tap-highlight-color.md)
- SVG color properties that are part of other specifications:
  - [`fill`](https://developer.mozilla.org/en-US/docs/Web/SVG/Attribute/fill)
  - [`flood-color`](https://developer.mozilla.org/en-US/docs/Web/SVG/Attribute/flood-color)
  - [`lighting-color`](https://developer.mozilla.org/en-US/docs/Web/SVG/Attribute/lighting-color)
  - [`stop-color`](https://developer.mozilla.org/en-US/docs/Web/SVG/Attribute/stop-color)
  - [`stroke`](https://developer.mozilla.org/en-US/docs/Web/SVG/Attribute/stroke)
- SVG
    [`color`](https://developer.mozilla.org/en-US/docs/Web/SVG/Attribute/color)
    attribute
- [Color
    wheel](https://developer.mozilla.org/en-US/docs/Glossary/Color_wheel)
    glossary term
- [Interpolation](https://developer.mozilla.org/en-US/docs/Glossary/Interpolation)
    glossary term
- The [`@font-palette-values`](@font-palette-values.md) at-rule
    [`override-colors`](override-colors.md) descriptor
- The [`@color-profile`](@color-profile.md) at-rule
- The [`color-gamut`](color-gamut.md) \@media feature
- The [`forced-colors`](forced-colors.md) \@media feature

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Color Module Level 4\
  ](https://drafts.csswg.org/css-color/)

[CSS Color Module Level 5\
  ](https://drafts.csswg.org/css-color-5/)
  -----------------------------------------------------------------------

See also
--------

- [CSS color adjustment](css_color_adjustment.md) module and the
    [`print-color-adjust`](print-color-adjust.md) property.
- [CSS images](css_images.md) module, which is where CSS
    [`<gradient>`](gradient.md) images are defined.
- The
    [`VideoColorSpace`](https://developer.mozilla.org/en-US/docs/Web/API/VideoColorSpace)
    interface
- The SVG
    [`<feColorMatrix>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/feColorMatrix)
    element
- [Canvas API: applying styles and
    colors](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Applying_styles_and_colors#colors)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_colors>
