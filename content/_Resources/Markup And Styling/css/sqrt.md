sqrt()
======

The `sqrt()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) is an exponential function that returns the
[square root](https://en.wikipedia.org/wiki/Square_root) of a number.

The function `pow(x, 0.5)` is equivalent to `sqrt(x)`.

Syntax
------

[css]

```css
/* A <number> value */
width: calc(100px * sqrt(9)); /*  300px */
width: calc(100px * sqrt(25)); /*  500px */
width: calc(100px * sqrt(100)); /* 1000px */
```

### Parameters

The `sqrt(x)` function accepts only one value as its parameter.

[`x`](#x)

:   A calculation which resolves to a [`<number>`](number.md) greater than
    or equal to 0.

### Return value

Returns a [`<number>`](number.md) which is the square root of `x`.

- if `x` is `+∞`, the result is `+∞`.
- If `x` is `0⁻`, the result is `0⁻`.
- If `x` is less than `0`, the result is `NaN`.

### Formal syntax

```
<sqrt()> = 
  sqrt( <calc-sum> )  

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

### Scale sizes based on square root

This example shows how you can use the `sqrt()` function to calculate
sizes.

#### HTML

[html]

```html
<div class="boxes">
  <div class="box">50px</div>
  <div class="box one">100px</div>
  <div class="box two">150px</div>
  <div class="box three">200px</div>
</div>
```

#### CSS

Here we are using [CSS custom properties](using_css_custom_properties.md)
to define the sizes to be used. First, we declare the first size
(`--size-0`), which is then used to calculate the other sizes.

- `--size-1` is calculated by multiplying the value of `--size-0`
    (50px) by the square root of 4 (2), which results in 100px.
- `--size-2` is calculated by multiplying the value of `--size-0`
    (50px) by the square root of 9 (3), which results in 150px.
- `--size-3` is calculated by multiplying the value of `--size-0`
    (50px) by the square root of 16 (4), which results in 200px.

[css]

```css
:root {
  --size-0: 50px;
  --size-1: calc(var(--size-0) * sqrt(4)); /*  100px */
  --size-2: calc(var(--size-0) * sqrt(9)); /*  150px */
  --size-3: calc(var(--size-0) * sqrt(16)); /*  200px */
}
```

The sizes are then applied as the `width` and `height` values of the
selectors.

[css]

```css
.one {
  width: var(--size-1);
  height: var(--size-1);
}
.two {
  width: var(--size-2);
  height: var(--size-2);
}
.three {
  width: var(--size-3);
  height: var(--size-3);
}
```

#### Result

Specifications
--------------

  -------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------

  [CSS Values and Units Module Level 4\
  [\#
  exponent-funcs]](https://drafts.csswg.org/css-values/#exponent-funcs)

  -------------------------------------------------------------------------------

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

`sqrt`

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

- [`pow()`](pow.md)
- [`hypot()`](hypot.md)
- [`log()`](log.md)
- [`exp()`](exp.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/sqrt>
