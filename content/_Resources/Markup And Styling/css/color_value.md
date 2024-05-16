\<color\>
=========

The `<color>` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[data type](css_types.md) represents a color. A `<color>` may also include
an [alpha-channel](https://en.wikipedia.org/wiki/Alpha_compositing)
*transparency value*, indicating how the color should
[composite](https://www.w3.org/TR/compositing-1/#simplealphacompositing)
with its background.

**Note:** Although `<color>` values are precisely defined, their actual
appearance may vary (sometimes significantly) from device to device.
This is because most devices are not calibrated, and some browsers do
not support output devices\' [color
profiles](https://en.wikipedia.org/wiki/ICC_profile).

Syntax
------

[css]

```css
/* Named colors */
rebeccapurple
aliceblue

/* RGB Hexadecimal */
#f09
#ff0099

/* RGB (Red, Green, Blue) */
rgb(255 0 153)
rgb(255 0 153 / 80%)

/* HSL (Hue, Saturation, Lightness) */
hsl(150 30% 60%)
hsl(150 30% 60% / 0.8)

/* HWB (Hue, Whiteness, Blackness) */
hwb(12 50% 0%)
hwb(194 0% 0% / 0.5)

/* LAB (Lightness, A-axis, B-axis) */
lab(50% 40 59.5)
lab(50% 40 59.5 / 0.5)

/* LCH (Lightness, Chroma, Hue) */
lch(52.2% 72.2 50)
lch(52.2% 72.2 50 / 0.5)

/* Oklab (Lightness, A-axis, B-axis) */
oklab(59% 0.1 0.1)
oklab(59% 0.1 0.1 / 0.5)

/* Oklch (Lightness, Chroma, Hue) */
oklch(60% 0.15 50)
oklch(60% 0.15 50 / 0.5)
```

A `<color>` value can be specified using one of the methods listed
below:

- By keywords: [`<named-color>`](named-color.md) (such as `blue` or
    `pink`), [`<system-color>`](system-color.md), and
    [`currentcolor`](#currentcolor_keyword).
- By hexadecimal notations: [`<hex-color>`](hex-color.md) (such as
    `#ff0000`).
- By parameters in a color space using functional notations:
  - [sRGB](https://en.wikipedia.org/wiki/SRGB) color space:
        [`hsl()`](hsl.md), [`hwb()`](hwb.md),
        [`rgb()`](rgb.md);
  - [CIELAB](https://en.wikipedia.org/wiki/CIELAB_color_space) color
        space: [`lab()`](lab.md), [`lch()`](lch.md);
  - [Oklab](https://bottosson.github.io/posts/oklab/) color space:
        [`oklab()`](oklab.md), [`oklch()`](oklch.md);
  - Other color spaces: [`color()`](_Resources/Markup%20And%20Styling/css/color_value/color.md).
- By mixing two colors: [`color-mix()`](color-mix.md).

### currentcolor keyword

The `currentcolor` keyword represents the value of an element\'s
[`color`](_Resources/Markup%20And%20Styling/css/color.md) property. This lets you use the `color` value on
properties that do not receive it by default.

If `currentcolor` is used as the value of the `color` property, it
instead takes its value from the inherited value of the `color`
property.

[html]

```html
<div style="color: blue; border: 1px dashed currentcolor;">
  The color of this text is blue.
  <div style="background: currentcolor; height:9px;"></div>
  This block is surrounded by a blue border.
</div>
```

### Missing color components

Each component of any CSS color functions - except for those using the
legacy comma-separated syntax - can be specified as the keyword `none`
to be a missing component.

Explicitly specifying missing components is useful in [color
interpolation](#interpolation_with_missing_components) for cases where
you would like to interpolate some color components but not others. For
all other purposes, a missing component will effectively have a zero
value in an appropriate unit: `0`, `0%`, or `0deg`. For example, the
following colors are equivalent when used outside of interpolation:

[css]

```css
/* These are equivalent */
color: oklab(50% none -0.25);
color: oklab(50% 0 -0.25);

/* These are equivalent */
background-color: hsl(none 100% 50%);
background-color: hsl(0deg 100% 50%);
```

Interpolation
-------------

Color interpolation happens with [gradients](gradient.md),
[transitions](using_css_transitions.md), and
[animations](using_css_animations.md).

When interpolating `<color>` values, they are first converted to a given
color space, and then each component of the [](computed_value.md) are interpolated linearly, with interpolation\'s
speed being determined by the [easing function](easing-function.md) in
transitions and animations. The interpolation color space defaults to
Oklab, but can be overridden through
[`<color-interpolation-method>`](color-interpolation-method.md) in some
color-related functional notations.

### Interpolation with missing components

#### Interpolating colors in the same space

When interpolating colors that are exactly in the interpolation color
space, missing components from one color are replaced with existing
values of the same components from the other color. For example, the
following two expressions are equivalent:

[css]

```css
color-mix(in oklch, oklch(none 0.2 10), oklch(60% none 30))
color-mix(in oklch, oklch(60% 0.2 10), oklch(60% 0.2 30))
```

**Note:** If a component is missing from both colors, this component
will be missing after the interpolation.

#### Interpolating colors from different spaces: analogous components

If any color to be interpolated is not in the interpolation color space,
its missing components are transferred into the converted color based on
**analogous components** of the same category as described in the
following table:

  Category       Analogous components
  -------------- ----------------------
  Reds           `R`, `X`
  Greens         `G`, `Y`
  Blues          `B`, `Z`
  Lightness      `L`
  Colorfulness   `C`, `S`
  Hue            `H`
  a              `a`
  b              `b`

For example:

- `X` (`0.2`) in `color(xyz 0.2 0.1 0.6)` is analogous to `R` (`50%`)
    in `rgb(50% 70% 30%)`.
- `H` (`0deg`) in `hsl(0deg 100% 80%)` is analogous to `H` (`140`) in
    `oklch(80% 0.1 140)`.

Using Oklch as the interpolation color space and the two colors below as
an example:

[css]

```css
lch(80% 30 none)
color(display-p3 0.7 0.5 none)
```

the preprocessing procedure is:

1. Replace the missing components in both colors with a zero value:

    [css]

    ```css
    lch(80% 30 0)
    color(display-p3 0.7 0.5 0)
    ```

2. Convert both colors into the interpolation color space:

    [css]

    ```css
    oklch(83.915% 0.0902 0.28)
    oklch(63.612% 0.1522 78.748)
    ```

3. If any component of the converted colors is analogous to a missing
    component in the corresponding original color, reset it as a missing
    component:

    [css]

    ```css
    oklch(83.915% 0.0902 none)
    oklch(63.612% 0.1522 78.748)
    ```

4. Replace any missing component with the same component from the other
    converted color:

    [css]

    ```css
    oklch(83.915% 0.0902 78.748)
    oklch(63.612% 0.1522 78.748)
    ```

Accessibility considerations
----------------------------

Some people have difficulty distinguishing colors. The [WCAG
2.2](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable/Use_of_color)
recommendation strongly advises against using color as the only means of
conveying a specific message, action, or result. See [color and color
contrast](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable/Color_contrast)
for more information.

Formal syntax
-------------

```
<color> = 
  <absolute-color-base>  |
  currentcolor           |
  <system-color>         

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

### Color value tester

In this example we provide a `<div>` and a text input. Entering a valid
color into the input causes the `<div>` to adopt that color, allowing
you to test our color values.

#### HTML

[html]

```html
<div></div>
<hr />
<label for="color">Enter a valid color value:</label>
<input type="text" id="color" />
```

#### Result

### Fully saturated sRGB colors

This example shows fully saturated sRGB colors in the sRGB color space.

#### HTML

[html]

```html
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
```

#### CSS

[css]

```css
div:nth-child(1) {
  background-color: hsl(0 100% 50%);
}
div:nth-child(2) {
  background-color: hsl(30 100% 50%);
}
div:nth-child(3) {
  background-color: hsl(60 100% 50%);
}
div:nth-child(4) {
  background-color: hsl(90 100% 50%);
}
div:nth-child(5) {
  background-color: hsl(120 100% 50%);
}
div:nth-child(6) {
  background-color: hsl(150 100% 50%);
}
div:nth-child(7) {
  background-color: hsl(180 100% 50%);
}
div:nth-child(8) {
  background-color: hsl(210 100% 50%);
}
div:nth-child(9) {
  background-color: hsl(240 100% 50%);
}
div:nth-child(10) {
  background-color: hsl(270 100% 50%);
}
div:nth-child(11) {
  background-color: hsl(300 100% 50%);
}
div:nth-child(12) {
  background-color: hsl(330 100% 50%);
}
```

#### Result

### Reds of different shades

This example shows reds of different shades in the sRGB color space.

#### HTML

[html]

```html
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
```

#### CSS

[css]

```css
div:nth-child(1) {
  background-color: hsl(0 100% 0%);
}
div:nth-child(2) {
  background-color: hsl(0 100% 20%);
}
div:nth-child(3) {
  background-color: hsl(0 100% 40%);
}
div:nth-child(4) {
  background-color: hsl(0 100% 60%);
}
div:nth-child(5) {
  background-color: hsl(0 100% 80%);
}
div:nth-child(6) {
  background-color: hsl(0 100% 100%);
  border: solid;
}
```

#### Result

### Reds of different saturations

This example shows reds of different saturations in the sRGB color
space.

#### HTML

[html]

```html
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
```

#### CSS

[css]

```css
div:nth-child(1) {
  background-color: hsl(0 0% 50%);
}
div:nth-child(2) {
  background-color: hsl(0 20% 50%);
}
div:nth-child(3) {
  background-color: hsl(0 40% 50%);
}
div:nth-child(4) {
  background-color: hsl(0 60% 50%);
}
div:nth-child(5) {
  background-color: hsl(0 80% 50%);
}
div:nth-child(6) {
  background-color: hsl(0 100% 50%);
}
```

#### Result

Specifications
--------------

  --------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------

  [CSS Color Module Level 4\
  [\#
  color-syntax]](https://drafts.csswg.org/css-color/#color-syntax)

  --------------------------------------------------------------------------

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

`color_value`

1

12

1

3

3.5

1

4.4

18

4

10.1

1

1.0

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

`color-contrast`

No

No

No

No

No

15

No

No

No

No

15

No

`color-mix`

111

111

113

No

97

16.2

111

111

113

No

16.2

22.0

`currentcolor`

1

12

1.5

9

9.5

4

37

18

4

14

3.2

1.0

`hsl`

1

12

1

9

9.5

3.1

≤37

18

4

10.1

2

1.0

`hsla`

1

12

3

9

10

3.1

≤37

18

4

10.1

2

1.0

`hwb`

101

101

96

No

87

15

101

101

96

70

15

19.0

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

`light-dark`

No

No

120

No

No

No

No

No

120

No

No

No

`named-color`

1

12

1

3Internet Explorer 8 and later support gray color keywords spelled with
an *e* (`grey`, `darkgrey`, `darkslategrey`, `dimgrey`, `lightgrey`, and
`lightslategrey`). Internet Explorer 3 to Internet Explorer 7 only
support the keywords spelled with *a* (`gray`, `darkgray`,
`darkslategray`, `dimgray`, `lightgray`, and `lightslategray`).

3.5

1

≤37

18

4

10.1

1

1.0

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

`rgb`

1

12

1

4

3.5

1

≤37

18

4

10.1

1

1.0

`rgb_hexadecimal_notation`

1

12

1

3

3.5

1

≤37

18

4

10.1

1

1.0

`rgba`

1

12

3

9

10

3.1

≤37

18

4

10.1

2

1.0

`system-color`

1

12

1

3

3.5

1

≤37

18

4

10.1

1

1.0

`transparent`

1

12

3

9

10

3.1

37

18

4

10.1

2

1.0

See also
--------

- [`opacity`](_Resources/Markup%20And%20Styling/css/opacity.md): the property defining transparency at the
    element level
- [`<hue>`](hue.md): the data type representing the hue angle of a color
- [`color`](_Resources/Markup%20And%20Styling/css/color.md), [`background-color`](background-color.md),
    [`border-color`](border-color.md), [`box-shadow`](box-shadow.md),
    [`outline-color`](outline-color.md), [`text-shadow`](text-shadow.md):
    common properties that use `<color>`
- [](applying_color.md)
- [New functions, gradients, and hues in CSS colors
    (Level 4)](https://developer.mozilla.org/en-US/blog/css-color-module-level-4/)
    on MDN blog (2023)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/color_value>
