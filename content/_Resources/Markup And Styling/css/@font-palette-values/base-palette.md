base-palette
============

The `base-palette` CSS
[descriptor](https://developer.mozilla.org/en-US/docs/Glossary/CSS_Descriptor)
is used to specify the name or index of a pre-defined palette to be used
for creating a new palette. If the specified `base-palette` does not
exist, then the palette defined at index 0 will be used.

Syntax
------

[css]

```css
@font-palette-values --one {
  base-palette: 1;
}
```

The `base-palette`
[descriptor](https://developer.mozilla.org/en-US/docs/Glossary/CSS_Descriptor)
is specified using a zero-based index of the font-maker created
palettes.

### Values

[`<index>`](#index)

:   Specifies the index of the pre-defined palette to use.

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
base-palette = 
  light            |
  dark             |
  <integer [0,∞]>  
```

Examples
--------

### Changing the default palette in a font

Using the [Rocher Color
Font](https://www.harbortype.com/fonts/rocher-color/), this example
shows two instances of switching the default palette in the font to an
alternate palette created by the font-maker.

#### HTML

[html]

```html
<h2>default base-palette</h2>
<h2 class="two">base-palette at index 2</h2>
<h2 class="five">base-palette at index 5</h2>
```

```css

#### CSS


[css]

```css

@font-face {
  font-family: "Rocher";
  src: url("[path-to-font]/RocherColorGX.woff2") format("woff2");
}

h2 {
  font-family: "Rocher";
}

@font-palette-values --two {
  font-family: "Rocher";
  base-palette: 2;
}

@font-palette-values --five {
  font-family: "Rocher";
  base-palette: 5;
}

.two {
  font-palette: --two;
}

.five {
  font-palette: --five;
}

```

#### Result

Specifications
--------------

  ------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------

  [CSS Fonts Module Level 4\
  [\#
  base-palette-desc]](https://drafts.csswg.org/css-fonts/#base-palette-desc)

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

See also
--------

- [`@font-palette-values`](@font-palette-values.md)
- [`font-family`](_Resources/Markup%20And%20Styling/css/@font-palette-values/font-family.md) descriptor
- [`override-colors`](override-colors.md) descriptor
- [`font-palette`](font-palette.md) property
- [`CSSFontPaletteValuesRule.basePalette`](https://developer.mozilla.org/en-US/docs/Web/API/CSSFontPaletteValuesRule/basePalette)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@font-palette-values/base-palette>
