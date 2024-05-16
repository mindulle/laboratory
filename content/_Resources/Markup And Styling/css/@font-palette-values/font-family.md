font-family
===========

The [\@font-palette-values](@font-palette-values.md)
[descriptor](https://developer.mozilla.org/en-US/docs/Glossary/CSS_Descriptor)
`font-family` is used to specify which font-family palette values are to
be applied to. This need to match exactly the values used when setting
the CSS [font-family](_Resources/Markup%20And%20Styling/css/font-family.md).

Syntax
------

[css]

```css
@font-palette-values --Dark-mode {
  font-family: "Bungee Spice";
  /* other palette settings follow */
}
```

Other palette values that follow apply only to the specified font
family. You can create [\@font-palette-values](@font-palette-values.md)
for other font families by using the same
[\<dashed-ident\>s](dashed-ident.md). This means that if you have
multiple Color Fonts and can use the same identifier for each.

### Values

[`<family-name>`](#family-name)

:   Specifies the name of the [font-family](_Resources/Markup%20And%20Styling/css/font-family.md).

Formal definition
-----------------

  ------------------------------------- ---------------------------------------------------
  Related [at-rule](at-rule.md)         [`@font-palette-values`](@font-palette-values.md)
  [Initial value](initial_value.md)     `n/a (required)`
  [Computed value](computed_value.md)   as specified
  ------------------------------------- ---------------------------------------------------

Formal syntax
-------------

```
font-family = 
  <family-name>#  
```

Examples
--------

### Using matching family names

In this example, when the `font-family` descriptor is used in the
[\@font-palette-values](@font-palette-values.md) at-rule, the same value
is used for the `font-family`, as when it is declared.

#### HTML

[html]

```html
<h2>This is spicy</h2>
<h2 class="extra-spicy">This is extra hot & spicy</h2>
```

#### CSS

[css]

```css
@import url(https://fonts.googleapis.com/css2?family=Bungee+Spice);
@font-palette-values --bungee-extra-spicy {
  font-family: "Bungee Spice";
  override-colors:
    0 DarkRed,
    1 Red;
}

h2 {
  font-family: "Bungee Spice";
}

h2.extra-spicy {
  font-palette: --bungee-extra-spicy;
}
```

#### Result

### Using the same palette identifier for multiple font-families

In this example, two [\@font-palette-values](@font-palette-values.md)
at-rules are set for two font families, but both the at-rules use the
same dashed-ident identifier, `--Dark Mode`. This helps to set the
[font-palette](font-palette.md) property for multiple elements, `h1` and
`h2` in this case, at the same time. This can be useful when you want to
update font colors to match your site\'s branding.

[css]

```css
@font-palette-values --Dark-Mode {
  font-family: "Bungee Spice";
  /* palette settings for Bungee Spice */
}

@font-palette-values --Dark-Mode {
  font-family: Bixa;
  /* palette settings for Bixa */
}

h1,
h2 {
  font-palette: --Dark-Mode;
}

h1 {
  font-family: "Bungee Spice";
}

h2 {
  font-family: Bixa;
}
```

Specifications
--------------

  --------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------

  [CSS Fonts Module Level 4\
  [\#
  font-family-2-desc]](https://drafts.csswg.org/css-fonts/#font-family-2-desc)

  --------------------------------------------------------------------------------------

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

`font-family`

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

- [`font-family`](_Resources/Markup%20And%20Styling/css/@font-face/font-family.md)
- [`@font-palette-values`](@font-palette-values.md)
- [`font-family`](_Resources/Markup%20And%20Styling/css/@font-palette-values/font-family.md) descriptor
- [`override-colors`](override-colors.md) descriptor
- [`font-palette`](font-palette.md) property
- [`CSSFontPaletteValuesRule.fontFamily`](https://developer.mozilla.org/en-US/docs/Web/API/CSSFontPaletteValuesRule/fontFamily)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@font-palette-values/font-family>
