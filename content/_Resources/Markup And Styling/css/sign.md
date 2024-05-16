sign()
======

The `sign()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) contains one calculation, and returns `-1` if
the numeric value of the argument is negative, `+1` if the numeric value
of the argument is positive, `0⁺` if the numeric value of the argument
is 0⁺, and `0⁻` if the numeric value of the argument is 0⁻.

**Note:** While `abs()` returns the absolute value of the argument,
`sign()` returns the sign of the argument.

Syntax
------

[css]

```css
/* property: sign( expression ) */
top: sign(20vh - 100px);
```

### Parameters

The `sign(x)` function accepts only one value as its parameter.

[`x`](#x)

:   A calculation which resolves to a number.

### Return value

A number representing the sign of `A`:

- If `x` is positive, returns `1`.
- If `x` is negative, returns `-1`.
- If `x` is positive zero, returns `0`.
- If `x` is negative zero, returns `-0`.
- Otherwise, returns `NaN`.

### Formal syntax

```
<sign()> = 
  sign( <calc-sum> )  

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

### Background image position

For example, in [`background-position`](background-position.md) positive
percentages resolve to a negative length, and vice versa, if the
background image is larger than the background area. Thus `sign(10%)`
might return `1` or `-1`, depending on how the percentage is resolved!
(Or even `0`, if it\'s resolved against a zero length.)

[css]

```css
div {
  background-position: sign(10%);
}
```

### Position direction

Another use case is to control the [`position`](position.md) of the
element. Either a positive or a negative value.

[css]

```css
div {
  position: absolute;
  top: calc(100px * sign(var(--value)));
}
```

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Values and Units Module Level 4\
  [\#
  sign-funcs]](https://drafts.csswg.org/css-values/#sign-funcs)

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

`sign`

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

- [`abs()`](abs.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/sign>
