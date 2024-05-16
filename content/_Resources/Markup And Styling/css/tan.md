tan()
=====

The `tan()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) is a trigonometric function that returns the
tangent of a number, which is a value between `−infinity` and
`infinity`. The function contains a single calculation that must resolve
to either a [`<number>`](number.md) or an [`<angle>`](angle.md) by
interpreting the result of the argument as radians.

Syntax
------

[css]

```css
/* Single <angle> values */
width: calc(100px * tan(45deg));
width: calc(100px * tan(0.125turn));
width: calc(100px * tan(0.785398163rad));

/* Single <number> values */
width: calc(100px * tan(0.5773502));
width: calc(100px * tan(1.732 - 1));

/* Other values */
width: calc(100px * tan(pi / 3));
width: calc(100px * tan(e));
```

### Parameter

The `tan(angle)` function accepts only one value as its parameter.

[`angle`](#angle)

:   A calculation which resolves to a [`<number>`](number.md) or an
    [`<angle>`](angle.md). When specifying unitless numbers they are
    interpreted as a number of radians, representing an
    [`<angle>`](angle.md).

### Return value

The tangent of an `angle` will always return a number between `−∞` and
`+∞`.

- If `angle` is `infinity`, `-infinity`, or `NaN`, the result is
    `NaN`.
- If `angle` is `0⁻`, the result is `0⁻`.
- If `angle` is one of the asymptote values (such as `90deg`,
    `270deg`, etc.), the result is *explicitly undefined*. Authors *must
    not* rely on `tan()` returning any particular value for these
    inputs.

### Formal syntax

```
<tan()> = 
  tan( <calc-sum> )  

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

### Drawing parallelograms

The `tan()` function can be used to draw a parallelogram with a given
bounding box.

#### HTML

[html]

```html
<div class="parallelogram"></div>
```

#### CSS

[css]

```css
.parallelogram {
  --w: 400;
  --h: 200;
  --angle: 30deg;
  position: relative;
  width: calc(1px * var(--w));
  height: calc(1px * var(--h));
}
.parallelogram::before {
  content: "";
  position: absolute;
  width: calc(100% - 100% * var(--h) / var(--w) * tan(var(--angle)));
  height: 100%;
  transform-origin: 0 100%;
  transform: skewX(calc(0deg - var(--angle)));
  background-color: red;
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

`tan`

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
- [`asin()`](asin.md)
- [`acos()`](acos.md)
- [`atan()`](atan.md)
- [`atan2()`](atan2.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/tan>
