mod()
=====

The `mod()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) returns a modulus left over when the first
parameter is divided by the second parameter, similar to the JavaScript
[remainder operator
(`%`)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Remainder).
The modulus is the value left over when one operand, the dividend, is
divided by a second operand, the divisor. It always takes the sign of
the divisor.

> For example, the CSS `mod(21, -4)` function returns the remainder of
> `-1`. When dividing 21 by -4, the result is 5 with a remainder of -1.
> The full calculation is `21 / -4 = -4 * 5 - 1`.

Syntax
------

[css]

```css
/* Unitless <number> */
line-height: mod(7, 2); /* 1 */
line-height: mod(14, 5); /* 4 */
line-height: mod(3.5, 2); /* 1.5 */

/* Unit based <percentage> and <dimension> */
margin: mod(15%, 2%); /* 1% */
margin: mod(18px, 4px); /* 2px */
margin: mod(19rem, 5rem); /* 4rem */
margin: mod(29vmin, 6vmin); /* 5vmin */
margin: mod(1000px, 29rem); /* 72px - if root font-size is 16px */

/* Negative/positive values */
rotate: mod(100deg, 30deg); /* 10deg */
rotate: mod(135deg, -90deg); /* -45deg */
rotate: mod(-70deg, 20deg); /* 10deg */
rotate: mod(-70deg, -15deg); /* -10deg */

/* Calculations */
scale: mod(10 * 2, 1.7); /* 1.3 */
rotate: mod(10turn, 18turn / 3); /* 4turn */
transition-duration: mod(20s / 2, 3000ms * 2); /* 4s */
```

### Parameter

The `mod(dividend, divisor)` function accepts two comma-separated values
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
representing the modulus, that is, the operation left over.

- If `divisor` is `0`, the result is `NaN`.
- If `dividend` is `infinite`, the result is `NaN`.
- If `divisor` is positive the result is positive (`0⁺`), and if
    `divisor` is negative the result is negative (`0⁻`).

### Formal syntax

```
<mod()> = 
  mod( <calc-sum> , <calc-sum> )  

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
  funcdef-mod]](https://drafts.csswg.org/css-values/#funcdef-mod)

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

`mod`

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
- [`rem()`](rem.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/mod>
