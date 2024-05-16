rem()
=====

The `rem()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) returns a remainder left over when the first
parameter is divided by the second parameter, similar to the JavaScript
[remainder operator
(`%`)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Remainder).
The remainder is the value left over when one operand, the dividend, is
divided by a second operand, the divisor. It always takes the sign of
the dividend.

> For example, the CSS `rem(27, 5)` function returns the remainder of
> `2`. When dividing 27 by 5, the result is 5 with a remainder of 2. The
> full calculation is `27 / 5 = 5 * 5 + 2`.

Syntax
------

[css]

```css
/* Unitless <number> */
line-height: rem(21, 2); /* 1 */
line-height: rem(14, 5); /* 4 */
line-height: rem(5.5, 2); /* 1.5 */

/* Unit based <percentage> and <dimension> */
margin: rem(14%, 3%); /* 2% */
margin: rem(18px, 5px); /* 3px */
margin: rem(10rem, 6rem); /* 4rem */
margin: rem(26vmin, 7vmin); /* 5vmin */
margin: rem(1000px, 29rem); /* 72px - if root font-size is 16px */

/* Negative/positive values */
rotate: rem(200deg, 30deg); /* 20deg */
rotate: rem(140deg, -90deg); /* 50deg */
rotate: rem(-90deg, 20deg); /* -10deg */
rotate: rem(-55deg, -15deg); /* -10deg */

/* Calculations */
scale: rem(10 * 2, 1.7); /* 1.3 */
rotate: rem(10turn, 18turn / 3); /* 4turn */
transition-duration: rem(20s / 2, 3000ms * 2); /* 4s */
```

### Parameter

The `rem(dividend, divisor)` function accepts two comma-separated values
as its parameters. Both parameters must have the same type,
[number](number.md), [dimension](dimension.md), or [percentage](percentage.md),
for the function to be valid. While the units in the two parameters
don\'t need to be the same, they do need of the same dimension type,
such as [`<length>`](length.md), [`<angle>`](angle.md), [`<time>`](time.md), or
[`<frequency>`](frequency.md) to be valid.

[`dividend`](#dividend)

:   A calculation that resolves to a [`<number>`](number.md),
    [`<dimension>`](dimension.md), or [`<percentage>`](percentage.md)
    representing the dividend.

[`divisor`](#divisor)

:   A calculation that resolves to a [`<number>`](number.md),
    [`<dimension>`](dimension.md), or [`<percentage>`](percentage.md)
    representing the divisor.

### Return value

Returns a [`<number>`](number.md), [`<dimension>`](dimension.md), or
[`<percentage>`](percentage.md) (corresponds to the parameters\' type)
representing the remainder, that is, the operation left over.

- If `divisor` is `0`, the result is `NaN`.
- If `dividend` is `infinite`, the result is `NaN`.
- If `dividend` is positive the result is positive (`0⁺`), and if
    `dividend` is negative the result is negative (`0⁻`).

### Formal syntax

```
<rem()> = 
  rem( <calc-sum> , <calc-sum> )  

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

Specifications
--------------

  -------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------

  [CSS Values and Units Module Level 4\
  [\#
  funcdef-rem]](https://drafts.csswg.org/css-values/#funcdef-rem)

  -------------------------------------------------------------------------

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

`rem`

No

No

118

No

No

15.4

No

No

118

No

15.4

No

See also
--------

- [`round()`](round.md)
- [`mod()`](mod.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/rem>
