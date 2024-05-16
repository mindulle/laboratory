sin()
=====

The `sin()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) is a trigonometric function that returns the
sine of a number, which is a value between `-1` and `1`. The function
contains a single calculation that must resolve to either a
[`<number>`](number.md) or an [`<angle>`](angle.md) by interpreting the result
of the argument as radians. That is, `sin(45deg)`, `sin(0.125turn)`, and
`sin(3.14159 / 4)` all represent the same value, approximately `0.707`.

Syntax
------

[css]

```css
/* Single <angle> values */
width: calc(100px * sin(45deg));
width: calc(100px * sin(0.25turn));
width: calc(100px * sin(1.0471967rad));

/* Single <number> values */
width: calc(100px * sin(63.673));
width: calc(100px * sin(2 * 0.125));

/* Other values */
width: calc(100px * sin(pi / 2));
width: calc(100px * sin(e / 4));
```

### Parameter

The `sin(angle)` function accepts only one value as its parameter.

[`angle`](#angle)

:   A calculation which resolves to a [`<number>`](number.md) or an
    [`<angle>`](angle.md). When specifying unitless numbers they are
    interpreted as a number of radians, representing an
    [`<angle>`](angle.md)

### Return value

The sine of an `angle` will always return a number between `−1` and `1`.

- If `angle` is `infinity`, `-infinity`, or `NaN`, the result is
    `NaN`.
- If `angle` is `0⁻`, the result is `0⁻`.

### Formal syntax

```
<sin()> = 
  sin( <calc-sum> )  

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

### Changing box sizes

In this example, `sin(30deg)` will return `0.5`, making the box have a
`50px` width and a `50px` height.

[css]

```css
div {
  background-color: red;
  width: calc(sin(30deg) * 100px);
  height: calc(sin(30deg) * 100px);
}
```

### Controlling animation duration

Another use case is to control the
[`animation-duration`](animation-duration.md), reducing the duration based
on the sine value. In this case, the animation duration will be `1s`.

[css]

```css
div {
  animation-name: myAnimation;
  animation-duration: calc(sin(0.25turn) * 1s);
}
```

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

`sin`

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

- [`cos()`](cos.md)
- [`tan()`](tan.md)
- [`asin()`](asin.md)
- [`acos()`](acos.md)
- [`atan()`](atan.md)
- [`atan2()`](atan2.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/sin>
