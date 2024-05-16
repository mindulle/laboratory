lch()
=====

The `lch()` functional notation expresses a given color in the LCH color
space. It has the same L axis as [`lab()`](lab.md), but uses polar
coordinates C (Chroma) and H (Hue).

Syntax
------

[css]

```css
lch(29.2345% 44.2 27);
lch(52.2345% 72.2 56.2);
lch(52.2345% 72.2 56.2 / .5);
```

### Values

Functional notation: `lch(L C H[ / A])`

[`L`](#l)

:   A [`<number>`](number.md) between `0` and `100`, a
    [`<percentage>`](percentage.md) between `0%` and `100%`, or the
    keyword `none`, which specifies the CIE Lightness. Here the number
    `0` corresponds to `0%` (black) and the number `100` corresponds to
    `100%` (white).

[`C`](#c)

:   A [`<number>`](number.md), a [`<percentage>`](percentage.md), or the
    keyword `none`, where `0%` is `0` and `100%` is the number `150`. It
    is a measure of the chroma (roughly representing the \"amount of
    color\"). Its minimum useful value is `0`, while its maximum is
    theoretically unbounded (but in practice does not exceed `230`).

[`H`](#h)

:   A [`<number>`](number.md), an [`<angle>`](angle.md), or the keyword
    `none`, which represents the hue angle. More details on this type
    can be found on the [`<hue>`](hue.md) reference.

[`A`](#a) [Optional]

:   An [`<alpha-value>`](alpha-value.md) or the keyword `none`, where
    the number `1` corresponds to `100%` (full opacity).

**Note:** Usually when percentage values have a numeric equivalent in
CSS, `100%` is equal to the number `1`. This case is notable where
`100%` is equal to the number `100` for the `L` value and `150` for the
`C` value.

**Note:** See [](color_value.md#missing_color_components) for the effect of
`none`.

### Formal syntax

```
<lch()> = 
  lch( [ <percentage> | <number> | none ] [ <percentage> | <number> | none ] [ <hue> | none ] [ / [ <alpha-value> | none ] ]? )  

<hue> = 
  <number>  |
  <angle>   

<alpha-value> = 
  <number>      |
  <percentage>  
```

Examples
--------

### Adjusting lightness, chroma, and hue with lch()

The following example shows the effect of varying the `L` (lightness),
`C` (chroma), and `H` (hue) values of the `lch()` functional notation.

#### HTML

[html]

```html
<div data-color="blue"></div>
<div data-color="blue-light"></div>

<div data-color="red"></div>
<div data-color="red-chroma"></div>

<div data-color="green"></div>
<div data-color="green-hue"></div>
```

#### CSS

[css]

```css
[data-color="blue"] {
  background-color: lch(0% 100 240);
}
[data-color="blue-light"] {
  background-color: lch(100% 100 240);
}

[data-color="red"] {
  background-color: lch(50% 130 20);
}
[data-color="red-chroma"] {
  background-color: lch(100% 30 20);
}

[data-color="green"] {
  background-color: lch(50% 132 130);
}
[data-color="green-hue"] {
  background-color: lch(50% 132 180);
}
```

#### Result

### Adjusting opacity with lch()

The following example shows the effect of varying the `A` (alpha) value
of the `lch()` functional notation. The `red` and `red-alpha` elements
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
  background-color: lch(50% 130 20);
}
[data-color="red-alpha"] {
  background-color: lch(50% 130 20 / 0.4);
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

`lch`

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

- [`<color>`](color_value.md): For a list of all color notations
- [LCH colors in CSS: what, why, and
    how?](https://lea.verou.me/2020/04/lch-colors-in-css-what-why-and-how/)
- [Safari Technology Preview 122 release
    notes](https://webkit.org/blog/11577/release-notes-for-safari-technology-preview-122/):
    includes `lch()` and [`lab()`](lab.md) colors

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/lch>
