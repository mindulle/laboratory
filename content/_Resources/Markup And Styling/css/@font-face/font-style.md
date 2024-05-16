font-style
==========

The `font-style` CSS descriptor allows authors to specify font styles
for the fonts specified in the [`@font-face`](@font-face.md) at-rule.

For a particular font family, authors can download various font faces
that correspond to the different styles of the same font family and then
use the `font-style` descriptor to explicitly specify the font face\'s
style. The values for this CSS descriptor are the same as that of the
corresponding [`font-style`](_Resources/Markup%20And%20Styling/css/font-style.md) property.

Syntax
------

[css]

```css
font-style: normal;
font-style: italic;
font-style: oblique;
font-style: oblique 30deg;
font-style: oblique 30deg 50deg;
```

### Values

[`normal`](#normal)

:   Selects the normal version of the font-family.

[`italic`](#italic)

:   Specifies that font-face is an italicized version of the normal
    font.

[`oblique`](#oblique)

:   Specifies that the font-face is an artificially sloped version of
    the normal font.

[`oblique`](#oblique_2) with angle

:   Selects a font classified as `oblique`, and additionally specifies
    an angle for the slant of the text.

[`oblique`](#oblique_3) with angle range

:   Selects a font classified as `oblique`, and additionally specifies a
    range of allowable angle for the slant of the text. Note that a
    range is only supported when the `font-style` is `oblique`; for
    `font-style: normal` or `italic`, no second value is allowed.

Formal definition
-----------------

  ------------------------------------- -------------------------------
  Related [at-rule](at-rule.md)         [`@font-face`](@font-face.md)
  [Initial value](initial_value.md)     `normal`
  [Computed value](computed_value.md)   as specified
  ------------------------------------- -------------------------------

Formal syntax
-------------

```
font-style = 
  auto                       |
  normal                     |
  italic                     |
  oblique [ <angle> ]?  
```

Examples
--------

### Specifying an italic font style

As an example, consider the garamond font family, in its normal form, we
get the following result:

[css]

```css
@font-face {
  font-family: garamond;
  src: url("garamond.ttf");
}
```

The italicized version of this text uses the same glyphs present in the
unstyled version, but they are artificially sloped by a few degrees.

On the other hand, if a true italicized version of the font family
exists, we can include it in the `src` descriptor and specify the font
style as italic, so that it is clear that the font is italicized. True
italics use different glyphs and are a bit different from their upright
counterparts, having some unique features and generally have a rounded
and calligraphic quality. These fonts are specially created by font
designers and are **not** artificially sloped.

[css]

```css
@font-face {
  font-family: garamond;
  src: url("garamond-italic.ttf");
  font-style: italic;
}
```

Specifications
--------------

  ------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------

  [CSS Fonts Module Level 4\
  [\#
  font-prop-desc]](https://drafts.csswg.org/css-fonts/#font-prop-desc)

  ------------------------------------------------------------------------------

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

`font-style`

4

12

3.5

4

10

3.1

≤37

18

4

10.1

2

1.0

See also
--------

- [`font-display`](_Resources/Markup%20And%20Styling/css/@font-face/font-display.md)
- [`font-family`](_Resources/Markup%20And%20Styling/css/@font-face/font-family.md)
- [`font-stretch`](_Resources/Markup%20And%20Styling/css/@font-face/font-stretch.md)
- [`font-weight`](_Resources/Markup%20And%20Styling/css/@font-face/font-weight.md)
- [`font-feature-settings`](_Resources/Markup%20And%20Styling/css/font-feature-settings.md)
- [`font-variation-settings`](_Resources/Markup%20And%20Styling/css/@font-face/font-variation-settings.md)
- [`src`](src.md)
- [`unicode-range`](unicode-range.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/font-style>
