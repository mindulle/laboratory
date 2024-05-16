color()
=======

The `color()` functional notation allows a color to be specified in a
particular, specified colorspace rather than the implicit sRGB
colorspace that most of the other color functions operate in.

Support for a particular colorspace can be detected with the
[`color-gamut`](color-gamut.md) CSS media feature.

Syntax
------

[css]

```css
color(display-p3 1 0.5 0);
color(display-p3 1 0.5 0 / .5);
```

### Values

Functional notation: `color(colorspace c1 c2 c3[ / A])`

[`colorspace`](#colorspace)

:   An [`<ident>`](ident.md) denoting one of the predefined color
    spaces: `srgb`, `srgb-linear`, `display-p3`, `a98-rgb`,
    `prophoto-rgb`, `rec2020`, `xyz`, `xyz-d50`, and `xyz-d65`.

[`c1`](#c1), `c2`, `c3`

:   [`<number>`](number.md) between 0 and 1, a
    [`<percentage>`](percentage.md) or the keyword `none`, which provide
    the component values in the color space.

[`A`](#a) [Optional]

:   An [`<alpha-value>`](alpha-value.md) or the keyword `none`, where
    the number `1` corresponds to `100%` (full opacity).

**Note:** See [](color_value.md#missing_color_components) for the effect of
`none`.

### Formal syntax

```
<color()> = 
  color( <colorspace-params> [ / [ <alpha-value> | none ] ]? )  

<colorspace-params> = 
  <predefined-rgb-params>  |
  <xyz-params>             

<alpha-value> = 
  <number>      |
  <percentage>  

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

### Using predefined colorspaces with color()

The following example shows the effect of varying the lightness, a-axis,
and b-axis values of the `color()` function.

#### HTML

[html]

```html
<div data-color="red-a98-rgb"></div>
<div data-color="red-prophoto-rgb"></div>
<div data-color="green-srgb-linear"></div>
<div data-color="green-display-p3"></div>
<div data-color="blue-rec2020"></div>
<div data-color="blue-srgb"></div>
```

#### CSS

[css]

```css
[data-color="red-a98-rgb"] {
  background-color: color(a98-rgb 1 0 0);
}
[data-color="red-prophoto-rgb"] {
  background-color: color(prophoto-rgb 1 0 0);
}
[data-color="green-srgb-linear"] {
  background-color: color(srgb-linear 0 1 0);
}
[data-color="green-display-p3"] {
  background-color: color(display-p3 0 1 0);
}
[data-color="blue-rec2020"] {
  background-color: color(rec2020 0 0 1);
}
[data-color="blue-srgb"] {
  background-color: color(srgb 0 0 1);
}
```

#### Result

### Using the xyz colorspace with color()

The following example shows how to use the `xyz` colorspace to specify a
color.

#### HTML

[html]

```html
<div data-color="red"></div>
<div data-color="green"></div>
<div data-color="blue"></div>
```

#### CSS

[css]

```css
[data-color="red"] {
  background-color: color(xyz 45 20 0);
}

[data-color="green"] {
  background-color: color(xyz-d50 0.3 80 0.3);
}

[data-color="blue"] {
  background-color: color(xyz-d65 5 0 50);
}
```

#### Result

### Using color-gamut media queries with color()

This example shows how to use the [`color-gamut`](color-gamut.md)
media query to detect support for a particular colorspace and use that
colorspace to specify a color.

#### HTML

[html]

```html
<div></div>
<div></div>
<div></div>
```

#### CSS

[css]

```css
@media (color-gamut: p3) {
  div {
    background-color: color(display-p3 0 0 1);
  }
}

@media (color-gamut: srgb) {
  div:nth-child(2) {
    background-color: color(srgb 0 0 1);
  }
}

@media (color-gamut: rec2020) {
  div:nth-child(3) {
    background-color: color(rec2020 0 0 1);
  }
}
```

#### Result

Specifications
--------------

  ------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------

  [CSS Color Module Level 4\
  [\#
  color-function]](https://drafts.csswg.org/css-color/#color-function)

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

`color`

111

111

113

No

97

15

10.1--15Only supports `display-p3` and `srgb` predefined color profiles.

111

111

113

No

15

10.3--15Only supports `display-p3` and `srgb` predefined color profiles.

22.0

See also
--------

- [The `<color>` data type](color_value.md) for a list of all color
    notations
- [`color-gamut`](color-gamut.md) media feature
- [Wide Gamut Color in CSS with
    Display-p3](https://webkit.org/blog/10042/wide-gamut-color-in-css-with-display-p3/)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/color>
