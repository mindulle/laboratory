\<color-interpolation-method\>
==============================

The `<color-interpolation-method>`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [](css_types.md) represents the color space used for interpolation
between [`<color>`](color_value.md) values. It can be used to override the
default interpolation color space for color-related functional notations
such as [`color-mix()`](color-mix.md) and
[`linear-gradient()`](linear-gradient.md).

When interpolating `<color>` values, the interpolation color space
defaults to Oklab.

Syntax
------

The `<color-interpolation-method>` specifies whether interpolation
should use a rectangular color space or a polar color space with an
optional hue interpolation method:

```
in <rectangular-color-space>
// or
in <polar-color-space>[ <hue-interpolation method>]
```

### Values

[`<rectangular-color-space>`](#rectangular-color-space)

:   One of the keywords `srgb`, `srgb-linear`, `lab`, `oklab`, `xyz`,
    `xyz-d50`, or `xyz-d65`.

[`<polar-color-space>`](#polar-color-space)

:   One of the keywords `hsl`, `hwb`, `lch`, or `oklch`.

[`<hue-interpolation-method>`](hue-interpolation-method.md) [Optional]

:   The algorithm for hue interpolation. It defaults to `shorter hue`.

Formal syntax
-------------

```
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

### Comparing interpolation color spaces using gradients

The following example shows the effect of using different interpolation
color spaces for [`linear-gradient()`](linear-gradient.md).

#### HTML

[html]

```html
<div>sRGB:</div>
<div class="gradient srgb"></div>
<div>Oklab:</div>
<div class="gradient oklab"></div>
<div>Oklch (with <code>longer hue</code>):</div>
<div class="gradient oklch-longer"></div>
```

#### CSS

[css]

```css
.gradient {
  height: 50px;
  width: 100%;
}
.srgb {
  background-image: linear-gradient(in srgb to right, blue, red);
}
.oklab {
  background-image: linear-gradient(in oklab to right, blue, red);
}
.oklch-longer {
  background-image: linear-gradient(in oklch longer hue to right, blue, red);
}
```

#### Result

Specifications
--------------

  ----------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------

  [CSS Color Module Level 4\
  [\#
  interpolation-space]](https://drafts.csswg.org/css-color/#interpolation-space)

  ----------------------------------------------------------------------------------------

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

`color-interpolation-method`

111

111

No

No

97

16.2

111

111

No

No

16.2

22.0

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

`color-interpolation-method`

111

111

No

No

97

16.2

111

111

No

No

16.2

22.0

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

`color-interpolation-method`

111

111

No

No

97

16.2

111

111

No

No

16.2

22.0

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

`color-interpolation-method`

111

111

No

No

97

16.2

111

111

No

No

16.2

22.0

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

`color-interpolation-method`

111

111

No

No

97

16.2

111

111

No

No

16.2

22.0

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

`color-interpolation-method`

111

111

No

No

97

16.2

111

111

No

No

16.2

22.0

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

`color-interpolation-method`

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

### css.types.color.color-mix

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

### css.types.image.gradient.conic-gradient.interpolation\_color\_space

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

### css.types.image.gradient.linear-gradient.interpolation\_color\_space

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

### css.types.image.gradient.radial-gradient.interpolation\_color\_space

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

### css.types.image.gradient.repeating-conic-gradient.interpolation\_color\_space

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

### css.types.image.gradient.repeating-linear-gradient.interpolation\_color\_space

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

### css.types.image.gradient.repeating-radial-gradient.interpolation\_color\_space

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

See also
--------

- [`<color>`](color_value.md), [`<gradient>`](gradient.md)
- [`<hue-interpolation-method>`](hue-interpolation-method.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/color-interpolation-method>
