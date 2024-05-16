\<gradient\>
============

The `<gradient>` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[data type](css_types.md) is a special type of [`<image>`](_Resources/Markup%20And%20Styling/css/image.md) that
consists of a progressive transition between two or more colors.

Try it
------

A CSS gradient has [no intrinsic dimensions](_Resources/Markup%20And%20Styling/css/image.md#description); i.e.,
it has no natural or preferred size, nor a preferred ratio. Its concrete
size will match the size of the element to which it applies.

Syntax
------

The `<gradient>` data type is defined with one of the function types
listed below.

### Linear gradient

Linear gradients transition colors progressively along an imaginary
line. They are generated with the
[`linear-gradient()`](linear-gradient.md) function.

### Radial gradient

Radial gradients transition colors progressively from a center point
(origin). They are generated with the
[`radial-gradient()`](radial-gradient.md) function.

### Repeating gradient

Repeating gradients duplicate a gradient as much as necessary to fill a
given area. They are generated with the
[`repeating-linear-gradient()`](repeating-linear-gradient.md) and
[`repeating-radial-gradient()`](repeating-radial-gradient.md)
functions.

### Conic gradient

Conic gradients transition colors progressively around a circle. They
are generated with the [`conic-gradient()`](conic-gradient.md)
function.

Interpolation
-------------

As with any interpolation involving colors, gradients are calculated in
the alpha-premultiplied color space. This prevents unexpected shades of
gray from appearing when both the color and the opacity are changing.
(Be aware that older browsers may not use this behavior when using the
[transparent keyword](named-color.md#transparent).)

Formal syntax
-------------

```
<gradient> = 
  <linear-gradient()>            |
  <repeating-linear-gradient()>  |
  <radial-gradient()>            |
  <repeating-radial-gradient()>  

<linear-gradient()> = 
  linear-gradient( [ <angle> | to <side-or-corner> ]? , <color-stop-list> )  

<radial-gradient()> = 
  radial-gradient( [ <ending-shape> || <size> ]? [ at <position> ]? , <color-stop-list> )  

<side-or-corner> = 
  [ left | right ]  ||
  [ top | bottom ]  

<color-stop-list> = 
  <linear-color-stop> , [ <linear-color-hint>? , <linear-color-stop> ]#  

<position> = 
  [ left | center | right ] || [ top | center | bottom ]  |
  [ left | center | right | <length-percentage> ] [ top | center | bottom | <length-percentage> ]?  |
  [ [ left | right ] <length-percentage> ] && [ [ top | bottom ] <length-percentage> ]  

<linear-color-stop> = 
  <color>               &&
  <length-percentage>?  

<linear-color-hint> = 
  <length-percentage>  

<length-percentage> = 
  <length>      |
  <percentage>  
```

Examples
--------

### Linear gradient example

A simple linear gradient.

[css]

```css
.linear-gradient {
  background: linear-gradient(
    to right,
    red,
    orange,
    yellow,
    green,
    blue,
    indigo,
    violet
  );
}
```

### Radial gradient example

A simple radial gradient.

[css]

```css
.radial-gradient {
  background: radial-gradient(red, yellow, rgb(30, 144, 255));
}
```

### Repeating gradient examples

Simple repeating linear and radial gradient examples.

[css]

```css
.linear-repeat {
  background: repeating-linear-gradient(
    to top left,
    lightpink,
    lightpink 5px,
    white 5px,
    white 10px
  );
}

.radial-repeat {
  background: repeating-radial-gradient(
    powderblue,
    powderblue 8px,
    white 8px,
    white 16px
  );
}
```

### Conic gradient example

A simple conic gradient example. Note that this isn\'t supported widely
across browser as of yet.

[css]

```css
.conic-gradient {
  background: conic-gradient(lightpink, white, powderblue);
}
```

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Images Module Level 4\
  [\#
  gradients]](https://drafts.csswg.org/css-images-4/#gradients)

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

`gradient`

2610

12

3.6Gradients are limited to
[`background-image`](https://developer.mozilla.org/docs/Web/CSS/background-image),
[`border-image`](https://developer.mozilla.org/docs/Web/CSS/border-image),
and
[`mask-image`](https://developer.mozilla.org/docs/Web/CSS/mask-image).

10

1512.111--15

75.1

≤37≤37

2618

4Gradients are limited to
[`background-image`](https://developer.mozilla.org/docs/Web/CSS/background-image),
[`border-image`](https://developer.mozilla.org/docs/Web/CSS/border-image),
and
[`mask-image`](https://developer.mozilla.org/docs/Web/CSS/mask-image).

1412.111--14

75

1.51.0

`conic-gradient`

69

79

83

No

56

12.1

69

69

83

48

12.2

10.0

`linear-gradient`

2610

12

49

16Before Firefox 36, gradients weren\'t applied on the pre-multiplied
color space, leading to shades of grey unexpectedly appearing when used
with transparency.

3.6\[\"Since Firefox 42, the prefixed version of gradients can be
disabled by setting `layout.css.prefixes.gradients` to `false`.\",
\"Considers `<angle>` to start to the right, instead of the top. I.e. it
considered an angle of `0deg` as a direction indicator pointing to the
right.\"\]

10Internet Explorer 5.5 through 9.0 supported gradients via a
proprietary filter:
`-ms-filter: progid:DXImageTransform.Microsoft.Gradient()`.

15Considers `<angle>` to start to the right, instead of the top. I.e. it
considered an angle of `0deg` as a direction indicator pointing to the
right.

12.1

11--15Considers `<angle>` to start to the right, instead of the top.
I.e. it considered an angle of `0deg` as a direction indicator pointing
to the right.

7

5.1\[\"Safari 4 was supporting an experimental
`-webkit-gradient(linear,…)` function. It is more limited than the later
standard version: you cannot specify both a position and an angle like
in `linear-gradient()`. This old outdated syntax is still supported for
compatibility purposes.\", \"Considers `<angle>` to start to the right,
instead of the top. I.e. it considered an angle of `0deg` as a direction
indicator pointing to the right.\"\]

≤37≤37

2618

49

16Before Firefox 36, gradients weren\'t applied on the pre-multiplied
color space, leading to shades of grey unexpectedly appearing when used
with transparency.

4\[\"Since Firefox 42, the prefixed version of gradients can be disabled
by setting `layout.css.prefixes.gradients` to `false`.\", \"Considers
`<angle>` to start to the right, instead of the top. I.e. it considered
an angle of `0deg` as a direction indicator pointing to the right.\"\]

14Considers `<angle>` to start to the right, instead of the top. I.e. it
considered an angle of `0deg` as a direction indicator pointing to the
right.

12.1

11--14Considers `<angle>` to start to the right, instead of the top.
I.e. it considered an angle of `0deg` as a direction indicator pointing
to the right.

7

5\[\"Safari 4 was supporting an experimental
`-webkit-gradient(linear,…)` function. It is more limited than the later
standard version: you cannot specify both a position and an angle like
in `linear-gradient()`. This old outdated syntax is still supported for
compatibility purposes.\", \"Considers `<angle>` to start to the right,
instead of the top. I.e. it considered an angle of `0deg` as a direction
indicator pointing to the right.\"\]

1.51.0

`radial-gradient`

2613

12

49

16Before Firefox 36, gradients weren\'t applied on the pre-multiplied
color space, leading to shades of grey unexpectedly appearing when used
with transparency.

3.6Since Firefox 42, the prefixed version of gradients can be disabled
by setting `layout.css.prefixes.gradients` to `false`.

10Internet Explorer 5.5 through 9.0 supported gradients via a
proprietary filter:
`-ms-filter: progid:DXImageTransform.Microsoft.Gradient()`.

1512.111.6--15

7

5.1Safari 4 was supporting an experimental `-webkit-gradient(radial,…)`
function. This old outdated syntax is still supported for compatibility
purposes.

≤37≤37

2618

49

16Before Firefox 36, gradients weren\'t applied on the pre-multiplied
color space, leading to shades of grey unexpectedly appearing when used
with transparency.

4Since Firefox 42, the prefixed version of gradients can be disabled by
setting `layout.css.prefixes.gradients` to `false`.

1412.112--14

7

5Safari 4 was supporting an experimental `-webkit-gradient(radial,…)`
function. This old outdated syntax is still supported for compatibility
purposes.

1.51.0

`repeating-conic-gradient`

69

79

83

No

56

12.1

69

69

83

48

12.2

10.0

`repeating-linear-gradient`

2610

12

49

16Before Firefox 36, gradients weren\'t applied on the pre-multiplied
color space, leading to shades of grey unexpectedly appearing when used
with transparency.

3.6\[\"Since Firefox 42, the prefixed version of gradients can be
disabled by setting `layout.css.prefixes.gradients` to `false`.\",
\"Considers `<angle>` to start to the right, instead of the top. I.e. it
considered an angle of `0deg` as a direction indicator pointing to the
right.\"\]

10Internet Explorer 5.5 through 9.0 supported gradients via a
proprietary filter:
`-ms-filter: progid:DXImageTransform.Microsoft.Gradient()`.

15Considers `<angle>` to start to the right, instead of the top. I.e. it
considered an angle of `0deg` as a direction indicator pointing to the
right.

12.1

11--15Considers `<angle>` to start to the right, instead of the top.
I.e. it considered an angle of `0deg` as a direction indicator pointing
to the right.

7

5.1\[\"Safari 4 was supporting an experimental
`-webkit-gradient(linear,…)` function. It is more limited than the later
standard version: you cannot specify both a position and an angle like
in `repeating-linear-gradient()`. This old outdated syntax is still
supported for compatibility purposes.\", \"Considers `<angle>` to start
to the right, instead of the top. I.e. it considered an angle of `0deg`
as a direction indicator pointing to the right.\"\]

≤37≤37

2618

49

16Before Firefox 36, gradients weren\'t applied on the pre-multiplied
color space, leading to shades of grey unexpectedly appearing when used
with transparency.

4\[\"Since Firefox 42, the prefixed version of gradients can be disabled
by setting `layout.css.prefixes.gradients` to `false`.\", \"Considers
`<angle>` to start to the right, instead of the top. I.e. it considered
an angle of `0deg` as a direction indicator pointing to the right.\"\]

14Considers `<angle>` to start to the right, instead of the top. I.e. it
considered an angle of `0deg` as a direction indicator pointing to the
right.

12.1

11--14Considers `<angle>` to start to the right, instead of the top.
I.e. it considered an angle of `0deg` as a direction indicator pointing
to the right.

7

5\[\"Safari 4 was supporting an experimental
`-webkit-gradient(linear,…)` function. It is more limited than the later
standard version: you cannot specify both a position and an angle like
in `repeating-linear-gradient()`. This old outdated syntax is still
supported for compatibility purposes.\", \"Considers `<angle>` to start
to the right, instead of the top. I.e. it considered an angle of `0deg`
as a direction indicator pointing to the right.\"\]

1.51.0

`repeating-radial-gradient`

2610

12

49

16Before Firefox 36, gradients weren\'t applied on the pre-multiplied
color space, leading to shades of grey unexpectedly appearing when used
with transparency.

3.6Since Firefox 42, the prefixed version of gradients can be disabled
by setting `layout.css.prefixes.gradients` to `false`.

10

1512.112--15

7

5.1Safari 4 was supporting an experimental `-webkit-gradient(radial,…)`
function. This old outdated syntax is still supported for compatibility
purposes.

≤374.4

2618

49

16Before Firefox 36, gradients weren\'t applied on the pre-multiplied
color space, leading to shades of grey unexpectedly appearing when used
with transparency.

10Since Firefox 42, the prefixed version of gradients can be disabled by
setting `layout.css.prefixes.gradients` to `false`.

1412.112--14

7

5Safari 4 was supporting an experimental `-webkit-gradient(radial,…)`
function. This old outdated syntax is still supported for compatibility
purposes.

1.51.0

See also
--------

- [Using CSS gradients](using_css_gradients.md)
- Gradient functions: [`linear-gradient()`](linear-gradient.md),
    [`repeating-linear-gradient()`](repeating-linear-gradient.md),
    [`radial-gradient()`](radial-gradient.md),
    [`repeating-radial-gradient()`](repeating-radial-gradient.md),
    [`conic-gradient()`](conic-gradient.md),
    [`repeating-conic-gradient()`](repeating-conic-gradient.md)
- [CSS Basic Data Types](css_types.md)
- [CSS Units and Values](css_values_and_units.md)
- [Introduction to CSS: Values and
    Units](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/gradient>
