\<hue\>
=======

The `<hue>` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[data type](css_types.md) represents the hue angle of a color. It is used
in the color functions that accept hue expressed as a single value,
specifically [`hsl()`](hsl.md), [`hwb()`](hwb.md),
[`lch()`](lch.md), and [`oklch()`](oklch.md)
functional notations.

The color wheel above shows hues at all angles in the
[sRGB](https://en.wikipedia.org/wiki/SRGB) color space. In particular,
*red* is at `0deg`, *yellow* is at `60deg`, *lime* is at `120deg`,
*cyan* is at `180deg`, *blue* is at `240deg`, and *magenta* is at
`300deg`.

**Note:** The angles corresponding to particular hues depend on the
color space. For example, the hue angle of sRGB green is `120deg` in the
sRGB color space, but `134.39deg` in the CIELAB color space.

The following table lists typical colors at various angles in the sRGB
(used by [`hsl()`](hsl.md) and [`hwb()`](hwb.md)),
CIELAB (used by [`lch()`](lch.md)), and Oklab (used by
[`oklch()`](oklch.md)) color spaces:

  -------------------
           0°
  -------- ----------
  sRGB

  CIELAB

Oklab
  -------------------

Syntax
------

A `<hue>` can be either an `<angle>` or a `<number>`.

### Values

[`<angle>`](angle.md)

:   An angle expressed in degrees, gradians, radians, or turns using the
    `deg`, `grad`, `rad`, or `turn`, respectively.

[`<number>`](#number)

:   A real number, representing degrees of the hue angle.

As an `<angle>` is periodic, `<hue>` is normalized to the range
`[0deg, 360deg)`. It implicitly wraps around such that `480deg` is the
same as `120deg`, `-120deg` is the same as `240deg`, `-1turn` is the
same as `1turn`, and so on.

### Interpolation

`<hue>` values are interpolated as [`<angle>`](angle.md) values, and the
default interpolation algorithm is
[`shorter`](hue-interpolation-method.md#values). In some color-related CSS
functions, this can be overridden by the
[`<hue-interpolation-method>`](hue-interpolation-method.md) component.

### Formal syntax

```
<hue> = 
  <number>  |
  <angle>   
```

Examples
--------

### Changing the hue of a color using a slider

The following example shows the effect of changing the `hue` value of
the [`hsl()`](hsl.md) functional notation on a color.

#### HTML

[html]

```html
<input type="range" min="0" max="360" value="0" id="hue-slider" />
<p>Hue: <span id="hue-value">0deg</span></p>
<div id="box"></div>
```

#### CSS

[css]

```css
#box {
  background-color: hsl(0 100% 50%);
}
```

#### JavaScript

[js]

```js
const hue = document.querySelector("#hue-slider");
const box = document.querySelector("#box");
hue.addEventListener("input", () => {
  box.style.backgroundColor = `hsl($ 100% 50%)`;
  document.querySelector("#hue-value").textContent = `$deg`;
});
```

#### Result

### Approximating red hues in different color spaces

The following example shows a similar red color in different color
spaces. The values in the `lch()` and `oklch()` functions are rounded
for readability.

#### HTML

[html]

```html
<div data-color="hsl-red">hsl()</div>
<div data-color="hwb-red">hwb()</div>
<div data-color="lch-red">lch()</div>
<div data-color="oklch-red">oklch()</div>
```

#### CSS

[css]

```css
[data-color="hsl-red"] {
  /* hsl(<hue> <saturation> <lightness>) */
  background-color: hsl(0 100% 50%);
}
[data-color="hwb-red"] {
  /* hwb(<hue> <whiteness> <blackness>) */
  background-color: hwb(0 0% 0%);
}
[data-color="lch-red"] {
  /* lch(<lightness> <chroma> <hue>) */
  background-color: lch(50 150 40);
}
[data-color="oklch-red"] {
  /* oklch(<lightness> <chroma> <hue>) */
  background-color: oklch(0.6 0.4 20);
}
```

#### Result

Specifications
--------------

  ------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------

  [CSS Color Module Level 4\
  [\#
  typedef-hue]](https://drafts.csswg.org/css-color/#typedef-hue)

  ------------------------------------------------------------------------

Browser compatibility
---------------------

See also
--------

- [`<color>`](color_value.md)
- [`<hue-interpolation-method>`](hue-interpolation-method.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/hue>
