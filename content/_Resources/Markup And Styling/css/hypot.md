hypot()
=======

The `hypot()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) is an exponential function that returns the
[square root](https://en.wikipedia.org/wiki/Square_root) of the sum of
squares of its parameters.

While [`pow()`](pow.md) and [`sqrt()`](sqrt.md) only work on unitless numbers,
`hypot()` accepts values with units, but they all must have the same
[type](css_types.md).

Syntax
------

[css]

```css
/* A <number> value */
width: hypot(2em); /* 2em */
width: hypot(3em, 4em); /* 5em */
width: hypot(30px, 40px); /* 50px */
width: hypot(48px, 64px); /* 80px */
width: hypot(3px, 4px, 5px); /* 7.0710678118654755px */
```

### Parameters

The `hypot(x [, ...]#)` function accepts one or more comma-separated
calculations as its parameters.

[`x`](#x), `x2`, \..., `xN`

:   A calculation that resolves to a [`<number>`](number.md),
    [`<dimension>`](dimension.md), or [`<percentage>`](percentage.md).

### Return value

Returns a [`<number>`](number.md), [`<dimension>`](dimension.md), or
[`<percentage>`](percentage.md) (based on the inputs), which is the square
root of the sum of squares of its parameters.

- If any of the inputs is `infinite`, the result is `+∞`.
- If a single parameter is provided, the result is the absolute value
    of its input. `hypot(2em)` and `hypot(-2em)` both resolve to `2em`.

### Formal syntax

```
<hypot()> = 
  hypot( <calc-sum># )  

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

### Sizes based on hypot function

This example shows how you can use the `hypot()` function to calculate
sizes.

#### HTML

[html]

```html
<div class="boxes">
  <div class="box">100px</div>
  <div class="box one">100px</div>
  <div class="box two">141.42px</div>
  <div class="box three">250px</div>
</div>
```

#### CSS

Here we are using [CSS custom properties](using_css_custom_properties.md)
to define the sizes to be used. First we declare the first size
(`--size-0`) which is then used to calculate the other sizes.

- `--size-1` is calculated with the hypotenuse of `--size-0` (100px).
    This takes the square value and, as there is no other value, returns
    the square root of the value, which results in 100px.
- `--size-2` is calculated with the hypotenuse of `--size-0` (100px),
    twice. This takes the square of the value (100px \* 100px =
    10000px^2^) and adds it to the square of `--size-0` again
    (10000px^2^ + 10000px^2^ = 20000px^2^) and returns the square root
    of the sum (√(20000px^2^)), which results in 141.42px.
- `--size-3` is calculated with the hypotenuse `--size-0` \* 1.5
    (150px) and `--size-0` \* 2 (200px). The result is the square root
    of the sum of their squares: The values are squared (22500px^2^ and
    40000px^2^) and added together (62500px^2^), with the sum
    square-rooted (√(62500px^2^)) being 250px.

[css]

```css
:root {
  --size-0: 100px;
  --size-1: hypot(var(--size-0)); /*  100px */
  --size-2: hypot(var(--size-0), var(--size-0)); /*  141.42px */
  --size-3: hypot(
    calc(var(--size-0) * 1.5),
    calc(var(--size-0) * 2)
  ); /*  250px */
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

`hypot`

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
- [`sqrt()`](sqrt.md)
- [`log()`](log.md)
- [`exp()`](exp.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/hypot>
