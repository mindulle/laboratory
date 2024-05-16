oklch()
=======

The `oklch()` functional notation expresses a given color in the Oklch
color space. It has the same L axis as [`oklab()`](oklab.md), but uses
polar coordinates C (Chroma) and H (Hue).

Syntax
------

[css]

```css
oklch(40.1% 0.123 21.57)
oklch(59.69% 0.156 49.77)
oklch(59.69% 0.156 49.77 / .5)
```

### Values

Functional notation: `oklch(L C H[ / A])`

[`L`](#l)

:   A [`<number>`](number.md) between `0` and `1`, a
    [`<percentage>`](percentage.md) between `0%` and `100%`, or the
    keyword `none`, where the number `0` corresponds to `0%` (black) and
    the number `1` corresponds to `100%` (white). `L` specifies the
    perceived lightness.

[`C`](#c)

:   A [`<number>`](number.md), a [`<percentage>`](percentage.md), or the
    keyword `none`, where `0%` is `0` and `100%` is the number `0.4`. It
    is a measure of the chroma (roughly representing the \"amount of
    color\"). Its minimum useful value is `0`, while the maximum is
    theoretically unbounded (but in practice does not exceed `0.5`).

[`H`](#h)

:   A [`<number>`](number.md), an [`<angle>`](angle.md), or the keyword
    `none`, which represents the hue angle. More details on this type
    can be found on the [`<hue>`](hue.md) reference.

[`A`](#a) [Optional]

:   An [`<alpha-value>`](alpha-value.md) or the keyword `none`, where
    the number `1` corresponds to `100%` (full opacity).

**Note:** See [](color_value.md#missing_color_components) for the effect of
`none`.

### Formal syntax

```
<oklch()> = 
  oklch( [ <percentage> | <number> | none ] [ <percentage> | <number> | none ] [ <hue> | none ] [ / [ <alpha-value> | none ] ]? )  

<hue> = 
  <number>  |
  <angle>   

<alpha-value> = 
  <number>      |
  <percentage>  
```

Examples
--------

### Adjusting the lightness, chroma, and hue of a color

The following example shows the effect of varying the `L` (lightness),
`C` (chroma), and `H` (hue) values of the `oklch()` color function.

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
  background-color: oklch(60% 0.4 240);
}
[data-color="blue-light"] {
  background-color: oklch(90% 0.4 240);
}

[data-color="red"] {
  background-color: oklch(100% 0.4 30);
}
[data-color="red-chroma"] {
  background-color: oklch(100% 0.3 40);
}

[data-color="green"] {
  background-color: oklch(60% 0.57 161);
}
[data-color="green-hue"] {
  background-color: oklch(60% 0.57 181);
}
```

#### Result

### Adjusting the alpha value of a color

The following example shows the effect of varying the `A` (alpha) value
of the `oklch()` color function. The `red` and `red-alpha` elements
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
  background-color: oklch(50% 0.5 20);
}
[data-color="red-alpha"] {
  background-color: oklch(50% 0.5 20 / 0.4);
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

`oklch`

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

- [`<color>`](color_value.md): For a list of all color notations
- [A perceptual color space for image
    processing](https://bottosson.github.io/posts/oklab/)
- [OKLCH in
    CSS](https://evilmartians.com/chronicles/oklch-in-css-why-quit-rgb-hsl)
- [Safari Technology Preview 137 release
    notes](https://webkit.org/blog/12156/release-notes-for-safari-technology-preview-137/):
    includes `oklch()` and [`oklab()`](oklab.md) colors

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/oklch>
