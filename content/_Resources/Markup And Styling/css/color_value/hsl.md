hsl()
=====

The `hsl()` functional notation expresses an
[sRGB](https://developer.mozilla.org/en-US/docs/Glossary/RGB) color
according to its *hue*, *saturation*, and *lightness* components. An
optional *alpha* component represents the color\'s transparency.

**Note:** The legacy `hsla()` syntax is an alias for `hsl()`, accepting
the same parameters and behaving in the same way.

Try it
------

Defining *complementary colors* with `hsl()` can be done with a single
formula, as they are positioned on the same diameter of the [color
wheel](https://developer.mozilla.org/en-US/docs/Glossary/Color_wheel).
If `θ` is the hue angle of a color, its complementary one will have
`180deg - θ` as its hue angle.

Syntax
------

[css]

```css
hsl(120deg 75% 25%)
hsl(120deg 75% 25% / 0.6)
```

The function also accepts a legacy syntax in which all values are
separated with commas.

### Values

Functional notation: `hsl(H S L[ / A])`

[`H`](#h)

:   A [`<number>`](number.md), an [`<angle>`](angle.md), or the keyword
    `none`, which represents the hue angle. More details on this type
    can be found on the [`<hue>`](hue.md) reference.

[`S`](#s)

:   A [`<percentage>`](percentage.md) or the keyword `none`, which
    represents saturation. Here `100%` is completely saturated, while
    `0%` is completely unsaturated (gray).

[`L`](#l)

:   A [`<percentage>`](percentage.md) or the keyword `none`, which
    represents lightness. Here `100%` is white, `0%` is black, and `50%`
    is \"normal\".

[`A`](#a) [Optional]

:   An [`<alpha-value>`](alpha-value.md) or the keyword `none`, where
    the number `1` corresponds to `100%` (full opacity).

**Note:** This functional notation serializes to sRGB values, and the
values of the red, green, blue components may be rounded in
serialization.

**Note:** See [](color_value.md#missing_color_components) for the effect of
`none`.

### Formal syntax

```
<hsl()> = 
  hsl( [ <hue> | none ] [ <percentage> | none ] [ <percentage> | none ] [ / [ <alpha-value> | none ] ]? )  |
  hsl( <hue> , <percentage> , <percentage> , <alpha-value>? )  |
  hsl( [ <hue> | none ] [ <percentage> | none ] [ <percentage> | none ] [ / [ <alpha-value> | none ] ]? )  

<hue> = 
  <number>  |
  <angle>   

<alpha-value> = 
  <number>      |
  <percentage>  
```

Examples
--------

### Using hsl() with conic-gradient()

The `hsl()` function works well with
[`conic-gradient()`](conic-gradient.md) as both deal with
angles.

#### CSS

[css]

```css
div {
  width: 100px;
  height: 100px;
  background: conic-gradient(
    hsl(360 100% 50%),
    hsl(315 100% 50%),
    hsl(270 100% 50%),
    hsl(225 100% 50%),
    hsl(180 100% 50%),
    hsl(135 100% 50%),
    hsl(90 100% 50%),
    hsl(45 100% 50%),
    hsl(0 100% 50%)
  );
  clip-path: circle(closest-side);
}
```

#### Result

### Legacy syntax: comma-separated values

For legacy reasons, the `hsl()` function accepts a form in which all
values are separated using commas.

#### HTML

[html]

```html
<div class="space-separated"></div>
<div class="comma-separated"></div>
```

#### CSS

[css]

```css
div {
  width: 100px;
  height: 50px;
  margin: 1rem;
}

div.space-separated {
  background-color: hsl(0 100% 50% / 50%);
}

div.comma-separated {
  background-color: hsl(0, 100%, 50%, 50%);
}
```

#### Result

### Legacy syntax: hsla()

The legacy `hsla()` syntax is an alias for `hsl()`.

#### HTML

[html]

```html
<div class="hsl"></div>
<div class="hsla"></div>
```

#### CSS

[css]

```css
div {
  width: 100px;
  height: 50px;
  margin: 1rem;
}

div.hsl {
  background-color: hsl(0 100% 50% / 50%);
}

div.hsla {
  background-color: hsla(0, 100%, 50%, 50%);
}
```

#### Result

Specifications
--------------

  ----------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------

  [CSS Color Module Level 4\
  [\#
  the-hsl-notation]](https://drafts.csswg.org/css-color/#the-hsl-notation)

  ----------------------------------------------------------------------------------

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

`alpha_parameter`

65

79

52

No

52

12.1

65

65

52

47

12.2

9.0

`space_separated_parameters`

65

79

52

No

52

12.1

65

65

52

47

12.2

9.0

See also
--------

- [`<color>`](color_value.md): the data type that represents any color
- [HSL Color Picker](https://hslpicker.com/)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/hsl>
