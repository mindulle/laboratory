Math.floor()
============

 
The `Math.floor()` static method always rounds down and returns the
largest integer less than or equal to a given number.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Math.floor(x)
```




 
### Parameters

 

[`x`](#x)

:   A number.



 
### Return value 

 
The largest integer smaller than or equal to `x`. It\'s the same value
as [`-Math.ceil(-x)`](ceil).



 
Description
-----------

 
Because `floor()` is a static method of `Math`, you always use it as
`Math.floor()`, rather than as a method of a `Math` object you created
(`Math` is not a constructor).



 
Examples
--------


 
### Using Math.floor() 

 
 
 
[js]


```js
Math.floor(-Infinity); // -Infinity
Math.floor(-45.95); // -46
Math.floor(-45.05); // -46
Math.floor(-0); // -0
Math.floor(0); // 0
Math.floor(4); // 4
Math.floor(45.05); // 45
Math.floor(45.95); // 45
Math.floor(Infinity); // Infinity
```




 
### Decimal adjustment 

 
In this example, we implement a method called `decimalAdjust()` that is
an enhancement method of `Math.floor()`, [`Math.ceil()`](ceil), and
[`Math.round()`](round). While the three `Math` functions always adjust
the input to the units digit, `decimalAdjust` accepts an `exp` parameter
that specifies the number of digits to the left of the decimal point to
which the number should be adjusted. For example, `-1` means it would
leave one digit after the decimal point (as in \"× 10^-1^\"). In
addition, it allows you to select the means of adjustment --- `round`,
`floor`, or `ceil` --- through the `type` parameter.

It does so by multiplying the number by a power of 10, then rounding the
result to the nearest integer, then dividing by the power of 10. To
better preserve precision, it takes advantage of Number\'s
[`toString()`](../number/tostring) method, which represents large or
small numbers in scientific notation (like `6.02e23`).

 
 
[js]


```js
/**
 * Adjusts a number to the specified digit.
 *
 * @param {"round" | "floor" | "ceil"} type The type of adjustment.
 * @param {number} value The number.
 * @param {number} exp The exponent (the 10 logarithm of the adjustment base).
 * @returns {number} The adjusted value.
 */
function decimalAdjust(type, value, exp) {
  type = String(type);
  if (!["round", "floor", "ceil"].includes(type)) {
    throw new TypeError(
      "The type of decimal adjustment must be one of 'round', 'floor', or 'ceil'.",
    );
  }
  exp = Number(exp);
  value = Number(value);
  if (exp % 1 !== 0 || Number.isNaN(value)) {
    return NaN;
  } else if (exp === 0) {
    return Math[type](value);
  }
  const [magnitude, exponent = 0] = value.toString().split("e");
  const adjustedValue = Math[type](`${magnitude}e${exponent - exp}`);
  // Shift back
  const [newMagnitude, newExponent = 0] = adjustedValue.toString().split("e");
  return Number(`${newMagnitude}e${+newExponent + exp}`);
}

// Decimal round
const round10 = (value, exp) => decimalAdjust("round", value, exp);
// Decimal floor
const floor10 = (value, exp) => decimalAdjust("floor", value, exp);
// Decimal ceil
const ceil10 = (value, exp) => decimalAdjust("ceil", value, exp);

// Round
round10(55.55, -1); // 55.6
round10(55.549, -1); // 55.5
round10(55, 1); // 60
round10(54.9, 1); // 50
round10(-55.55, -1); // -55.5
round10(-55.551, -1); // -55.6
round10(-55, 1); // -50
round10(-55.1, 1); // -60
// Floor
floor10(55.59, -1); // 55.5
floor10(59, 1); // 50
floor10(-55.51, -1); // -55.6
floor10(-51, 1); // -60
// Ceil
ceil10(55.51, -1); // 55.6
ceil10(51, 1); // 60
ceil10(-55.59, -1); // -55.5
ceil10(-59, 1); // -50
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-math.floor]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-math.floor)

  ---------------------------------------------------------------------------------------------------


Browser compatibility 
---------------------

 


Desktop

Mobile

Server

Chrome

Edge

Firefox

Opera

Safari

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

WebView Android

Deno

Node.js

`floor`

1

12

1

3

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

 
See also 
--------

 
-   [`Math.abs()`](abs)
-   [`Math.ceil()`](ceil)
-   [`Math.round()`](round)
-   [`Math.sign()`](sign)
-   [`Math.trunc()`](trunc)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/floor>

