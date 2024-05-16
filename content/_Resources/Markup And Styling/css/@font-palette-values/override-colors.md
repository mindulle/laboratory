override-colors
===============

The `override-colors` CSS
[descriptor](https://developer.mozilla.org/en-US/docs/Glossary/CSS_Descriptor)
is used to override colors in the chosen [base-palette](base-palette.md)
for a color font.

Syntax
------

[css]

```css
/* basic syntax */
override-colors: <index of color> <color>;

/* using color names */
override-colors: 0 red;

/* using hex-color */
override-colors: 0 #f00;

/* using rgb */
override-colors: 0 rgb(255, 0, 0);

/* overriding multiple colors */
override-colors:
  0 #f00,
  1 #0f0,
  2 #00f;

/* overriding multiple colors with readability */
override-colors:
  0 #f00,
  1 #0f0,
  2 #00f;
```

The `override-colors`
[descriptor](https://developer.mozilla.org/en-US/docs/Glossary/CSS_Descriptor)
takes a comma-separated list of the color index and new color value.

The color index is zero-based and any [color value](color_value.md) can
be used.

For each key-value pair of index and color, the color with the index in
the specified [base-palette](base-palette.md) will be overwritten. If the
color font does not have a color at the specified index, it will be
ignored.

### Values

[`[ <integer [0,∞]> <absolute-color-base> ]`](#_integer_0%E2%88%9E_absolute-color-base_)

:   Specifies the index of a color in a [base-palette](base-palette.md) and
    the color to overwrite it with.

Formal definition
-----------------

  ------------------------------------- ---------------------------------------------------
  Related [at-rule](at-rule.md)         [`@font-palette-values`](@font-palette-values.md)
  [Initial value](initial_value.md)     `n/a (required)`
  [Computed value](computed_value.md)   as specified
  ------------------------------------- ---------------------------------------------------

Formal syntax
-------------

```text
override-colors = 
  [ <integer [0,∞]> <absolute-color-base> ]#  

<absolute-color-base> = 
  <hex-color>                |
  <absolute-color-function>  |
  <named-color>              |
  transparent                

<absolute-color-function> = 
  <rgb()>    |
  <rgba()>   |
  <hsl()>    |
  <hsla()>   |
  <hwb()>    |
  <lab()>    |
  <lch()>    |
  <oklab()>  |
  <oklch()>  |
  <color()>  

<rgb()> = 
  rgb( [ <percentage> | none ] [ / [ <alpha-value> | none ] ]? )  |
  rgb( [ <number> | none ] [ / [ <alpha-value> | none ] ]? )  |
  rgb( <percentage># , <alpha-value>? )            |
  rgb( <number># , <alpha-value>? )                |
  rgb( [ <percentage> | none ] [ / [ <alpha-value> | none ] ]? )  |
  rgb( [ <number> | none ] [ / [ <alpha-value> | none ] ]? )  

<hsl()> = 
  hsl( [ <hue> | none ] [ <percentage> | none ] [ <percentage> | none ] [ / [ <alpha-value> | none ] ]? )  |
  hsl( <hue> , <percentage> , <percentage> , <alpha-value>? )  |
  hsl( [ <hue> | none ] [ <percentage> | none ] [ <percentage> | none ] [ / [ <alpha-value> | none ] ]? )  

<hwb()> = 
  hwb( [ <hue> | none ] [ <percentage> | none ] [ <percentage> | none ] [ / [ <alpha-value> | none ] ]? )  

<lab()> = 
  lab( [ <percentage> | <number> | none ] [ <percentage> | <number> | none ] [ <percentage> | <number> | none ] [ / [ <alpha-value> | none ] ]? )  

<lch()> = 
  lch( [ <percentage> | <number> | none ] [ <percentage> | <number> | none ] [ <hue> | none ] [ / [ <alpha-value> | none ] ]? )  

<oklab()> = 
  oklab( [ <percentage> | <number> | none ] [ <percentage> | <number> | none ] [ <percentage> | <number> | none ] [ / [ <alpha-value> | none ] ]? )  

<oklch()> = 
  oklch( [ <percentage> | <number> | none ] [ <percentage> | <number> | none ] [ <hue> | none ] [ / [ <alpha-value> | none ] ]? )  

<color()> = 
  color( <colorspace-params> [ / [ <alpha-value> | none ] ]? )  

<alpha-value> = 
  <number>      |
  <percentage>  

<hue> = 
  <number>  |
  <angle>   

<colorspace-params> = 
  <predefined-rgb-params>  |
  <xyz-params>             

<predefined-rgb-params> = 
  <predefined-rgb> [ <number> | <percentage> | none ]  

<xyz-params> = 
  <xyz-space> [ <number> | <percentage> | none ]  

<predefined-rgb> = 
  srgb          |
  srgb-linear   |
  display-p3    |
  a98-rgb       |
  prophoto-rgb  |
  rec2020       

<xyz-space> = 
  xyz      |
  xyz-d50  |
  xyz-d65  
```

Examples
--------

### Changing colors of emojis

This example shows how to override colors in the [Noto Color
Emoji](https://fonts.google.com/noto/specimen/Noto+Color+Emoji/) color
font to match your site\'s brand.

#### HTML

[html]

```html
<section class="hats">
  <div class="hat">
    <h2>Original Hat</h2>
    <div class="emoji">🎩</div>
  </div>
  <div class="hat">
    <h2>Red Hat</h2>
    <div class="emoji red-hat">🎩</div>
  </div>
</section>
```

#### CSS

[css]

```css
@font-face {
  font-family: "Noto Color Emoji";
  font-style: normal;
  font-weight: 400;
  src: url(https://fonts.gstatic.com/l/font?kit=Yq6P-KqIXTD0t4D9z1ESnKM3-HpFabts6diywYkdG3gjD0U&skey=a373f7129eaba270&v=v24)
    format("woff2");
}

.emoji {
  font-family: "Noto Color Emoji";
  font-size: 3rem;
}
@font-palette-values --red {
  font-family: "Noto Color Emoji";
  override-colors:
    0 rgb(74, 11, 0),
    1 rgb(149, 22, 1),
    2 rgb(183, 27, 1),
    3 rgb(193, 28, 1),
    4 rgb(230, 34, 1);
}
.red-hat {
  font-palette: --red;
}
```

#### Result

### Changing a color in an alternate base-palette

Using [Rocher Color
Font](https://www.harbortype.com/fonts/rocher-color/), this example
shows how to override one color in the font.

#### HTML

[html]

```html
<h2 class="normal-palette">Normal Palette</h2>
<h2 class="override-palette">Override Palette</h2>
```

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
@font-palette-values --override-palette {
  font-family: "Rocher";
  base-palette: 3;
}
@font-palette-values --override-palette {
  font-family: "Rocher";
  base-palette: 3;
  override-colors: 0 rebeccapurple;
}
.normal-palette {
  font-palette: --normal-palette;
}
.override-palette {
  font-palette: --override-palette;
}
```

#### Result

This example shows the that in `base-palette` `3`, the color at index 0
is overridden with `rebeccapurple`.

Specifications
--------------

  ------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------

  [CSS Fonts Module Level 4\
  [\#
  override-color]](https://drafts.csswg.org/css-fonts/#override-color)

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

- [`@font-palette-values`](@font-palette-values.md)
- [`base-palette`](base-palette.md)
- [`font-family`](_Resources/Markup%20And%20Styling/css/@font-palette-values/font-family.md)
- [`font-palette`](font-palette.md)
- [`CSSFontPaletteValuesRule.overrideColors`](https://developer.mozilla.org/en-US/docs/Web/API/CSSFontPaletteValuesRule/overrideColors)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@font-palette-values/override-colors>
