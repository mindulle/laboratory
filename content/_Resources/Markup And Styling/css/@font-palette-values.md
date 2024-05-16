\@font-palette-values
=====================

The `@font-palette-values`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[at-rule](at-rule.md) allows you to customize the default values of
[font-palette](font-palette.md) created by the font-maker.

Syntax
------

[css]

```css
@font-palette-values --identifier {
  font-family: Bixa;
}
.my-class {
  font-palette: --identifier;
}
```

The [\<dashed-ident\>](dashed-ident.md) is a user defined identifier, that
while it looks like a [CSS custom property](using_css_custom_properties.md)
behaves in a different way and is not wrapped in a [](var().md).

### Descriptors

[font-family](_Resources/Markup%20And%20Styling/css/@font-palette-values/font-family.md)

:   Specifies the name of the font family that this palette can be
    applied to.

[base-palette](base-palette.md)

:   Specifies the name or index of the base-palette, created by the
    font-maker, to use.

[override-colors](override-colors.md)

:   Specifies the colors in the base palette to override.

Formal definition
-----------------

[Value not found in DB!]

Formal syntax
-------------

```
@font-palette-values = 
  @font-palette-values <dashed-ident>   
```

Examples
--------

### Overriding colors in an existing palette

This example shows how you can change some or all of the colors in a
color font.

#### HTML

[html]

```html
<p>default colors</p>
<p class="alternate">alternate colors</p>
```

#### CSS

[css]

```css
@import url(https://fonts.googleapis.com/css2?family=Bungee+Spice);
p {
  font-family: "Bungee Spice";
  font-size: 2rem;
}
@font-palette-values --Alternate {
  font-family: "Bungee Spice";
  override-colors:
    0 #00ffbb,
    1 #007744;
}
.alternate {
  font-palette: --Alternate;
}
```

#### Result

When overriding colors of the normal or base-palette at index 0 you do
not need to declare which base-palette to use. This should only be done
when overriding a different base-palette. If you are overriding all the
colors then there is also no need to specify the base-palette to use.

Specifications
--------------

  --------------------------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------------------------

  [CSS Fonts Module Level 4\
  [\#
  at-ruledef-font-palette-values]](https://drafts.csswg.org/css-fonts/#at-ruledef-font-palette-values)

  --------------------------------------------------------------------------------------------------------------

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

`@font-palette-values`

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

`base-palette`

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

`override-colors`

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

- [`font-palette`](font-palette.md) property
- [`font-family`](_Resources/Markup%20And%20Styling/css/@font-palette-values/font-family.md) descriptor
- [`base-palette`](base-palette.md) descriptor
- [`override-colors`](override-colors.md) descriptor
- [`CSSFontPaletteValuesRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSFontPaletteValuesRule)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@font-palette-values>
