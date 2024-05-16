pow()
=====

The `pow()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) is an exponential function that returns the
value of a base raised to the power of a number.

The [`exp()`](exp.md) function is a special case of `pow()` where the value
of the base is the mathematical constant
[e](https://en.wikipedia.org/wiki/E_(mathematical_constant)).

Syntax
------

[css]

```css
/* A <number> value */
width: calc(10px * pow(5, 2)); /* 10px * 25 = 250px */
width: calc(10px * pow(5, 3)); /* 10px * 125 = 1250px */
width: calc(10px * pow(2, 10)); /* 10px * 1024 = 10240px */
```

### Parameters

The `pow(base, number)` function accepts two comma-separated values as
its parameters.

[`base`](#base)

:   A calculation that resolves to a [`<number>`](number.md), representing
    the base.

[`number`](#number)

:   A calculation that resolves to a [`<number>`](number.md), representing
    the exponent.

### Return value

Returns a [`<number>`](number.md) representing base^number^, that is,
`base` raised to the power of `number`.

Formal syntax
-------------

```
<pow()> = 
  pow( <calc-sum> , <calc-sum> )  

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

### Scale headings by fixed ratio

The `pow()` function can be useful for strategies like CSS Modular
Scale, which relates all the font-sizes on a page to each other by a
fixed ratio.

#### HTML

[html]

```html
<h1>Heading 1</h1>
<h2>Heading 2</h2>
<h3>Heading 3</h3>
<h4>Heading 4</h4>
<h5>Heading 5</h5>
<h6>Heading 6</h6>
```

#### CSS

[css]

```css
h1 {
  font-size: calc(1rem * pow(1.5, 4));
}
h2 {
  font-size: calc(1rem * pow(1.5, 3));
}
h3 {
  font-size: calc(1rem * pow(1.5, 2));
}
h4 {
  font-size: calc(1rem * pow(1.5, 1));
}
h5 {
  font-size: calc(1rem * pow(1.5, 0));
}
h6 {
  font-size: calc(1rem * pow(1.5, -1));
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

`pow`

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

- [`sqrt()`](sqrt.md)
- [`hypot()`](hypot.md)
- [`exp()`](exp.md)
- [`log()`](log.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/pow>
