oklab()
=======

The `oklab()` functional notation expresses a given color in the Oklab
color space, which attempts to mimic how color is perceived by the human
eye. The `oklab()` works with a Cartesian coordinate system on the Oklab
color space, the a- and b-axes. If you want a polar color system, chroma
and hue, use [`oklch()`](oklch.md).

Oklab is a perceptual color space and is useful to:

- Transform an image to grayscale, without changing its lightness.
- Modify the saturation of colors, while keeping user perception of
    hue and lightness
- Create smooth and uniform gradients of colors (when interpolated
    manually, for example, in a
    [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas)
    element).

The function `oklab()` can represent any color from the Oklab color
space that is wider than RGB and include wide gamut and P3 colors.

Syntax
------

[css]

```css
oklab(40.1% 0.1143 0.045);
oklab(59.69% 0.1007 0.1191);
oklab(59.69% 0.1007 0.1191 / 0.5);
```

### Values

Functional notation: `oklab(L a b[ / A])`

[`L`](#l)

:   A [`<number>`](number.md) between `0` and `1`, a
    [`<percentage>`](percentage.md) between `0%` and `100%`, or the
    keyword `none`, where the number `0` corresponds to `0%` (black) and
    the number `1` corresponds to `100%` (white). `L` specifies the
    perceived lightness.

[`a`](#a)

:   A [`<number>`](number.md) between `-0.4` and `0.4`, a
    [`<percentage>`](percentage.md) between `-100%` and `100%`, or the
    keyword `none`. It specifies the distance along the `a` axis in the
    Oklab colorspace, that is, how green or red the color is.

[`b`](#b)

:   A [`<number>`](number.md) between `-0.4` and `0.4`, a
    [`<percentage>`](percentage.md) between `-100%` and `100%`, or the
    keyword `none`. It specifies the distance along the `b` axis in the
    Oklab colorspace, that is, how blue or yellow the color is.

[`A`](#a_2) [Optional]

:   An [`<alpha-value>`](alpha-value.md) or the keyword `none`, where
    the number `1` corresponds to `100%` (full opacity).

**Note:** See [](color_value.md#missing_color_components) for the effect of
`none`.

### Formal syntax

```
<oklab()> = 
  oklab( [ <percentage> | <number> | none ] [ <percentage> | <number> | none ] [ <percentage> | <number> | none ] [ / [ <alpha-value> | none ] ]? )  

<alpha-value> = 
  <number>      |
  <percentage>  
```

Examples
--------

### Adjusting the lightness and axes with oklab()

The following example shows the effect of varying the lightness, a-axis,
and b-axis values of the `oklab()` function.

#### HTML

[html]

```html
<div data-color="blue"></div>
<div data-color="blue-light"></div>

<div data-color="red"></div>
<div data-color="red-a"></div>

<div data-color="green"></div>
<div data-color="green-b"></div>
```

#### CSS

[css]

```css
[data-color="blue"] {
  background-color: oklab(0.5 -0.3 -0.4);
}
[data-color="blue-light"] {
  background-color: oklab(0.7 -0.3 -0.4);
}

[data-color="red"] {
  background-color: oklab(100% 0.4 0.4);
}
[data-color="red-a"] {
  background-color: oklab(100% 0.2 0.4);
}

[data-color="green"] {
  background-color: oklab(100% -100% 0.4);
}
[data-color="green-b"] {
  background-color: oklab(100% -100% 0.6);
}
```

#### Result

### Adjusting opacity with oklab()

The following example shows the effect of varying the `A` (alpha) value
of the `oklab()` function. The `red` and `red-alpha` elements overlap
the `#background-div` element to demonstrate the effect of opacity.
Giving the `red-alpha` element an opacity of `0.4` makes it appear more
transparent than the `red` element.

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
  background-color: oklab(0.628 0.225 0.126);
}
[data-color="red-alpha"] {
  background-color: oklab(0.628 0.225 0.126 / 0.4);
}
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Color Module Level 4\
  [\# ok-lab]](https://drafts.csswg.org/css-color/#ok-lab)

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

`oklab`

111

111

113

No

97

15.4

111

111

113

No

15.4

22.0

See also
--------

- The [`<color>` data type](color_value.md) for a list of all color
    notations
- [`oklch()`](oklch.md): Another functional notation using the same color
    space as `oklab()` but in a polar coordinate system
- [A perceptual color space for image
    processing](https://bottosson.github.io/posts/oklab/) on
    bottosson.github.io (2023)
- [OKLAB color
    wheel](https://observablehq.com/@shan/oklab-color-wheel) on
    observablehq.com

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/oklab>
