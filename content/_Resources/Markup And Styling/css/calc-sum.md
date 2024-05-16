\<calc-sum\>
============

The `<calc-sum>` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[data type](css_types.md) represents an expression which performs a
calculation in any [CSS math function](css_functions.md#math_functions).
The expression executes a basic arithmetic operation of addition and
subtraction between two values.

Syntax
------

The `<calc-sum>` type defines two numeric values and one of the
following [arithmetic
operators](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/Math#arithmetic_operators)
between them.

[`+`](#sect1)

:   Adds two numbers together.

[`-`](#-)

:   Subtracts the right number from the left.

### Formal syntax

```
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

<calc-sum> = 
  <calc-product> [ [ '+' | '-' ] <calc-product> ]*  
```

Description
-----------

The operands in the expression may be any [`<length>`](length.md) syntax
value. You can use [`<length>`](length.md), [`<frequency>`](frequency.md),
[`<angle>`](angle.md), [`<time>`](time.md), [`<percentage>`](percentage.md),
[`<number>`](number.md), or [`<integer>`](integer.md).

Different unit types can be used in a single expression. For example,
subtracting `px` from `%`, as in `calc(100% - 10px)`, is a valid
expression.

Including [CSS variables](css_cascading_variables.md) in `calc-sum`
expressions is also allowed. The following code
`calc(10px + var(--variable))`, is a valid expression.

The `+` and `-` operators **must be surrounded by
[whitespace](https://developer.mozilla.org/en-US/docs/Glossary/Whitespace)**.
For instance, `calc(50% -8px)` will be parsed as a percentage followed
by a negative length --- an invalid expression --- while
`calc(50% - 8px)` is a percentage followed by a subtraction operator and
a length. Likewise, `calc(8px + -50%)` is treated as a length followed
by an addition operator and a negative percentage.

Specifications
--------------

**No specification found**

No specification data found for `css.types.calc-sum`.\
[Check for problems with this page](#on-github) or contribute a missing
`spec_url` to
[mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).
Also make sure the specification is included in
[w3c/browser-specs](https://github.com/w3c/browser-specs).

Browser compatibility
---------------------

See also
--------

- [`<calc-product>`]
- [`<calc-value>`]
- [`<calc-constant>`](calc-constant.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/calc-sum>
