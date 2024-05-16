asin()
======

The `asin()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) is a trigonometric function that returns the
inverse sine of a number between `-1` and `1`. The function contains a
single calculation that returns the number of radians representing an
[`<angle>`](angle.md) between `-90deg` and `90deg`.

Syntax
------

[css]

```css
/* Single <number> values */
transform: rotate(asin(-0.2));
transform: rotate(asin(2 * 0.125));

/* Other values */
transform: rotate(asin(pi / 5));
transform: rotate(asin(e / 3));
```

### Parameter

The `asin(number)` function accepts only one value as its parameter.

[`number`](#number)

:   A calculation which resolves to a [`<number>`](number.md) between `-1`
    and `1`.

### Return value

The inverse sine of an `number` will always return an [`<angle>`](angle.md)
between `-90deg` and `90deg`.

- If `number` is less than `-1` or greater than `1`, the result is
    `NaN`.
- If `number` is `0⁻`, the result is `0⁻`.

### Formal syntax

```
<asin()> = 
  asin( <calc-sum> )  

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

The `asin()` function can be used to
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
  transform: rotate(asin(1));
}
div.box-2 {
  transform: rotate(asin(0.5));
}
div.box-3 {
  transform: rotate(asin(0));
}
div.box-4 {
  transform: rotate(asin(-0.5));
}
div.box-5 {
  transform: rotate(asin(-1));
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

`asin`

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
- [`acos()`](acos.md)
- [`atan()`](atan.md)
- [`atan2()`](atan2.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/asin>
