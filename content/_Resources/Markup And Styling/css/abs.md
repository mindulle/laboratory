abs()
=====

The `abs()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) returns the absolute value of the argument, as
the same type as the input.

Syntax
------

[css]

```css
/* property: abs(expression) */
width: abs(20% - 100px);
```

### Parameters

The `abs(x)` function accepts only one value as its parameter.

[`x`](#x)

:   A calculation which resolves to a number.

### Return value

The absolute value of `x`.

- if `x`\'s numeric value is positive or `0⁺`, return `x`.
- Otherwise, returns `-1 * x`.

### Formal syntax

```
<abs()> = 
  abs( <calc-sum> )  

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

### Positive variables

The `abs()` function can be used to ensure that a value is always
positive. In the following example a CSS custom property `--font-size`
is used as the value of [`font-size`](font-size.md). Wrapping this custom
property in `abs()` will convert a negative value to a positive one.

[css]

```css
h1 {
  font-size: abs(var(--font-size));
}
```

### Control gradient angle of direction

You can also control the gradient direction using `abs()` function. In
the following example, with an angle of -45deg the gradient would start
red and transition to blue. By using `abs()` to make the value positive,
the gradient will start blue and transition to red.

[css]

```css
div {
  --deg: -45deg;
  background-image: linear-gradient(abs(var(--deg)), blue, red);
}
```

### Backwards compatible fallback

In older browsers that lack the support for CSS `abs()` function, you
can use the CSS [`max()`](max.md) function to achieve the same result, as
shown below:

[css]

```css
p {
  line-height: max(var(--lh), -1 * var(--lh));
}
```

We use the [`max()`](max.md) function to return the largest (most positive)
value from a list of two values: `var(--lh)` or `-1 * var(--lh)`.
Irrespective of whether `--lh` is positive or negative, the calculated
return value will always be positive, that is, an absolute number.

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

`abs`

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

- [`sign()`](sign.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/abs>
