lab()
=====

The `lab()` functional notation expresses a given color in the CIE
L\*a\*b\* color space. Lab represents the entire range of color that
humans can see.

Syntax
------

[css]

```css
lab(29.2345% 39.3825 20.0664);
lab(52.2345% 40.1645 59.9971);
lab(52.2345% 40.1645 59.9971 / .5);
```

### Values

Functional notation: `lab(L a b[ / A])`

[`L`](#l)

:   A [`<number>`](number.md) between `0` and `100`, a
    [`<percentage>`](percentage.md) between `0%` and `100%`, or the
    keyword `none`, which specifies the CIE Lightness. Here the number
    `0` corresponds to `0%` (black) and the number `100` corresponds to
    `100%` (white).

[`a`](#a)

:   A [`<number>`](number.md) between `-125` and `125`, a
    [`<percentage>`](percentage.md) between `-100%` and `100%`, or the
    keyword `none`, which specifies the distance along the `a` axis in
    the CIELAB colorspace, that is how green/red the color is.

[`b`](#b)

:   A [`<number>`](number.md) between `-125` and `125`, a
    [`<percentage>`](percentage.md) between `-100%` and `100%`, or the
    keyword `none`, which specifies the distance along the `b` axis in
    the CIELAB colorspace, that is how blue/yellow the color is.

[`A`](#a_2) [Optional]

:   An [`<alpha-value>`](alpha-value.md) or the keyword `none`, where
    the number `1` corresponds to `100%` (full opacity).

**Note:** Usually when percentage values have a numeric equivalent in
CSS, `100%` is equal to the number `1`. This case is notable where
`100%` is equal to the number `100` for the `L` value and `125` for the
`a` and `b` values.

**Note:** See [](color_value.md#missing_color_components) for the effect of
`none`.

### Formal syntax

```
<lab()> = 
  lab( [ <percentage> | <number> | none ] [ <percentage> | <number> | none ] [ <percentage> | <number> | none ] [ / [ <alpha-value> | none ] ]? )  

<alpha-value> = 
  <number>      |
  <percentage>  
```

Examples
--------

### Adjusting lightness and color axes with lab()

The following example shows the effect of varying the lightness, a-axis,
and b-axis values of the `lab()` function.

#### HTML

[html]

```html
<div data-color="red"></div>
<div data-color="red-a"></div>

<div data-color="green"></div>
<div data-color="green-b"></div>

<div data-color="blue"></div>
<div data-color="blue-light"></div>
```

#### CSS

[css]

```css
[data-color="red"] {
  background-color: lab(100 125 125);
}
[data-color="red-a"] {
  background-color: lab(100 110 125);
}

[data-color="green"] {
  background-color: lab(75% -120 125);
}
[data-color="green-b"] {
  background-color: lab(75% -120 10);
}

[data-color="blue"] {
  background-color: lab(0 -120 -120);
}
[data-color="blue-light"] {
  background-color: lab(70 -120 -120);
}
```

#### Result

### Adjusting opacity with lab()

The following example shows the effect of varying the `A` (alpha) value
of the `lab()` functional notation. The `red` and `red-alpha` elements
overlap the `#background-div` element to demonstrate the effect of
opacity. Giving `A` a value of `0.4` makes the color 40% opaque.

#### HTML

[html]

```html
<div id="background-div">
  <div data-color="red"></div>
  <div data-color="red-alpha"></div>
</div>
```

#### CSS

[css]

```css
[data-color="red"] {
  background-color: lab(100 125 125);
}
[data-color="red-alpha"] {
  background-color: lab(100 125 125 / 0.4);
}
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Color Module Level 4\
  [\#
  lab-colors]](https://drafts.csswg.org/css-color/#lab-colors)

  -----------------------------------------------------------------------

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

`lab`

111

111

113

No

97

15

111

111

113

No

15

22.0

See also
--------

- The [`<color>` data type](color_value.md) for a list of all color
    notations
- [LCH colors in CSS: what, why, and
    how?](https://lea.verou.me/2020/04/lch-colors-in-css-what-why-and-how/)
- [Safari Technology Preview 122 release
    notes](https://webkit.org/blog/11577/release-notes-for-safari-technology-preview-122/):
    includes `lab()` and [`lch()`](lch.md) colors

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/lab>
