atan2()
=======

The `atan2()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) is a trigonometric function that returns the
inverse tangent of two values between `-infinity` and `infinity`. The
function accepts two arguments and returns the number of radians
representing an [`<angle>`](angle.md) between `-180deg` and `180deg`.

Syntax
------

[css]

```css
/* Two <number> values */
transform: rotate(atan2(3, 2));

/* Two <dimension> values */
transform: rotate(atan2(1rem, -0.5rem));

/* Two <percentage> values */
transform: rotate(atan2(20%, -30%));

/* Other values */
transform: rotate(atan2(pi, 45));
transform: rotate(atan2(e, 30));
```

### Parameters

The `atan2(y, x)` function accepts two comma-separated values as its
parameters. Each value can be a [`<number>`](number.md), a
[`<dimension>`](dimension.md), or a [`<percentage>`](percentage.md). Both
values must be of the same type, although if they are
[`<dimension>`](dimension.md) they can be of different units (example:
`atan2(100px, 5vw)` is valid).

[`y`](#y)

:   The y-coordinate of the point. A calculation which resolves to a
    [`<number>`](number.md), a [`<dimension>`](dimension.md), or a
    [`<percentage>`](percentage.md).

[`x`](#x)

:   The x-coordinate of the point. A calculation which resolves to a
    [`<number>`](number.md), a [`<dimension>`](dimension.md), or a
    [`<percentage>`](percentage.md).

### Return value

Given two values `x` and `y`, the function `atan2(y, x)` calculates and
returns the [`<angle>`](angle.md) between the positive x-axis and the ray
from the origin to the point `(x, y)`.

### Formal syntax

```
<atan2()> = 
  atan2( <calc-sum> , <calc-sum> )  

<calc-sum> = 
  <calc-product> [ [ '+' | '-' ] <calc-product> ]*  

<calc-product> = 
  <calc-value> [ [ '*' | '/' ] <calc-value> ]*  

<calc-value> = 
  <number>         |
  <dimension>      |
  <percentage>     |
  <calc-constant>  |
  ( <calc-sum> )   

<calc-constant> = 
  e          |
  pi         |
  infinity   |
  -infinity  |
  NaN        
```

Examples
--------

### Rotate elements

The `atan2()` function can be used to
[`rotate`](_Resources/Markup%20And%20Styling/css/transform-function/rotate.md) elements as it return an
[`<angle>`](angle.md).

#### HTML

[html]

```html
<div class="box box-1"></div>
<div class="box box-2"></div>
<div class="box box-3"></div>
<div class="box box-4"></div>
<div class="box box-5"></div>
```

#### CSS

[css]

```css
div.box {
  width: 100px;
  height: 100px;
  background: linear-gradient(orange, red);
}
div.box-1 {
  transform: rotate(atan2(3, 2));
}
div.box-2 {
  transform: rotate(atan2(3%, -2%));
}
div.box-3 {
  transform: rotate(atan2(-1, 0.5));
}
div.box-4 {
  transform: rotate(atan2(1, 0.5));
}
div.box-5 {
  transform: rotate(atan2(1rem, -0.5rem));
}
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Values and Units Module Level 4\
  [\#
  trig-funcs]](https://drafts.csswg.org/css-values/#trig-funcs)

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

`atan2`

111

111

108

No

97

15.4

111

111

108

No

15.4

22.0

See also
--------

- [`sin()`](sin.md)
- [`cos()`](cos.md)
- [`tan()`](tan.md)
- [`asin()`](asin.md)
- [`acos()`](acos.md)
- [`atan()`](atan.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/atan2>
