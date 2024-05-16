color-mix()
===========

The `color-mix()` functional notation takes two
[`<color>`](color_value.md) values and returns the result of mixing them
in a given colorspace by a given amount.

Syntax
------

[css]

```css
color-mix(in lch, plum, pink);
color-mix(in lch, plum 40%, pink);
color-mix(in srgb, #34c9eb 20%, white);
color-mix(in hsl longer hue, hsl(120 100% 50%) 20%, white);
```

### Values

Functional notation: `color-mix(method, color1[ p1], color2[ p2])`

[`method`](#method)

:   A [`<color-interpolation-method>`](color-interpolation-method.md)
    specifying the interpolation color space.

[`color1`](#color1), `color2`

:   [`<color>`](color_value.md) values to mix.

[`p1`](#p1), `p2` [Optional]

:   [`<percentage>`](percentage.md) values between `0%` and `100%`,
    specifying the amount of each color to mix. They are normalized as
    follows:

    -   If both `p1` and `p2` are omitted, then `p1 = p2 = 50%`.
    -   If `p1` is omitted, then `p1 = 100% - p2`.
    -   If `p2` is omitted, then `p2 = 100% - p1`.
    -   If `p1 = p2 = 0%`, the function is invalid.
    -   If `p1 + p2 ≠ 100%`, then `p1' = p1 / (p1 + p2)` and
        `p2' = p2 / (p1 + p2)`, where `p1'` and `p2'` are the
        normalization results.

### Formal syntax

```
<color-mix()> = 
  color-mix( <color-interpolation-method> , [ <color> && <percentage [0,100]>? ]# )  

<color-interpolation-method> = 
  in [ <rectangular-color-space> | <polar-color-space> <hue-interpolation-method>? ]  

<rectangular-color-space> = 
  srgb         |
  srgb-linear  |
  lab          |
  oklab        |
  xyz          |
  xyz-d50      |
  xyz-d65      

<polar-color-space> = 
  hsl    |
  hwb    |
  lch    |
  oklch  

<hue-interpolation-method> = 
  [ shorter | longer | increasing | decreasing ] hue  
```

Examples
--------

### Mixing two colors

In a supporting browser, the items have more blue, and therefore less
white, as a higher percentage of `#34c9eb` is mixed in. When no value is
given, the percentage defaults to 50%.

#### HTML

[html]

```html
<ul>
  <li>0%</li>
  <li>25%</li>
  <li>50%</li>
  <li>75%</li>
  <li>100%</li>
  <li></li>
</ul>
```

#### CSS

[css]

```css
li:nth-child(1) {
  background-color: color-mix(in srgb, #34c9eb 0%, white);
}

li:nth-child(2) {
  background-color: color-mix(in srgb, #34c9eb 25%, white);
}

li:nth-child(3) {
  background-color: color-mix(in srgb, #34c9eb 50%, white);
}

li:nth-child(4) {
  background-color: color-mix(in srgb, #34c9eb 75%, white);
}

li:nth-child(5) {
  background-color: color-mix(in srgb, #34c9eb 100%, white);
}

li:nth-child(6) {
  background-color: color-mix(in srgb, #34c9eb, white);
}
```

#### Result

### Using hue interpolation in color-mix()

When using shorter hue interpolation, the resulting hue angle is halfway
between the input angles when taking the shortest route around the color
wheel. The longer hue interpolation method results in a hue angle which
is the midpoint when taking the longer route around the color wheel. For
more information, see
[`<hue-interpolation-method>`](hue-interpolation-method.md).

[html]

```html
<div class="color-one">color one</div>
<div class="color-two">color two</div>
<div class="shorter">mixed shorter</div>
<div class="longer">mixed longer</div>
```

#### CSS

[css]

```css
.color-one {
  background-color: hsl(10 100% 50%);
}
.color-two {
  background-color: hsl(60 100% 50%);
}
.shorter {
  background-color: color-mix(
    in hsl shorter hue,
    hsl(10 100% 50%),
    hsl(60 100% 50%)
  );
}
.longer {
  background-color: color-mix(
    in hsl longer hue,
    hsl(10 100% 50%),
    hsl(60 100% 50%)
  );
}
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Color Module Level 5\
  [\#
  color-mix]](https://drafts.csswg.org/css-color-5/#color-mix)

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

See also
--------

- [`<color>`](color_value.md)
- [`<color-interpolation-method>`](color-interpolation-method.md)
- [`<hue>`](hue.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/color-mix>
