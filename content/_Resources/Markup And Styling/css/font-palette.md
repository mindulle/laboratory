font-palette
============

The `font-palette`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property allows
specifying one of the many palettes contained in a font that a user
agent should use for the font. Users can also override the values in a
palette or create a new palette by using the
[\@font-palette-values](@font-palette-values.md) at-rule.

Syntax
------

[css]

```css
/* Using a font-defined palette */
font-palette: normal;

/* Using a user-defined palette */
font-palette: --one;
```

### Values

[`normal`](#normal)

:   Specifies the default color palette or the default glyph
    colorization (set by the font maker) to be used for the font. With
    this setting, the palette in the font at index 0 is rendered.

[`light`](#light)

:   Specifies the first palette in the font that matches \'light\' to be
    used for the font. Some fonts contain metadata that identify a
    palette as applicable for a light (close to white) background. If a
    font does not have this metadata, the `light` value behaves as
    `normal`.

[`dark`](#dark)

:   Specifies the first palette in the font that matches \'dark\' to be
    used for the font. Some fonts contain metadata that identify a
    palette as applicable for a dark (close to black) background. If a
    font does not have this metadata, the value behaves as `normal`.

[`<palette-identifier>`](#palette-identifier)

:   Allows you to specify your own values for the font palette by using
    the [\@font-palette-values](@font-palette-values.md) at-rule. This
    value is specified using the [\<dashed-ident\>](dashed-ident.md)
    format.

Formal definition
-----------------

  ---------------------------------- ------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `normal`
  Applies to                         all elements and text. It also applies to [`::first-letter`](::first-letter) and [`::first-line`](::first-line).
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- ------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
font-palette = 
  normal                |
  light                 |
  dark                  |
  <palette-identifier>  
```

Examples
--------

### Specifying a dark palette

This example allows you to use the first palette marked as *dark* (works
best on a near black background) by the font-maker.

[css]

```css
@media (prefers-color-scheme: dark) {
  .banner {
    font-palette: dark;
  }
}
```

Specifications
--------------

  ------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------

  [CSS Fonts Module Level 4\
  [\#
  font-palette-prop]](https://drafts.csswg.org/css-fonts/#font-palette-prop)

  ------------------------------------------------------------------------------------

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

`font-palette`

101

101

107

No

87

15.4

101

101

107

70

15.4

19.0

See also
--------

- [`@font-palette-values`](@font-palette-values.md)
- [`base-palette`](base-palette.md) descriptor
- [`font-family`](_Resources/Markup%20And%20Styling/css/@font-palette-values/font-family.md) descriptor
- [`override-colors`](override-colors.md) descriptor

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/font-palette>
