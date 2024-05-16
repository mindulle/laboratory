Math.hypot()
============

 
The `Math.hypot()` static method returns the square root of the sum of
squares of its arguments. That is,

$$\mathtt{\operatorname{Math.hypot}(v_{1},v_{2},\ldots,v_{n})} = \sqrt{\sum\limits_{i = 1}^{n}v_{i}^{2}} = \sqrt{v_{1}^{2} + v_{2}^{2} + \ldots + v_{n}^{2}}$$


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Math.hypot()
Math.hypot(value1)
Math.hypot(value1, value2)
Math.hypot(value1, value2, /* …, */ valueN)
```




 
### Parameters

 

[`value1`](#value1), ..., `valueN`

:   Numbers.



 
### Return value 

 
The square root of the sum of squares of the given arguments. Returns
[`Infinity`](../infinity) if any of the arguments is ±Infinity.
Otherwise, if at least one of the arguments is or is converted to
[`NaN`](../nan), returns [`NaN`](../nan). Returns `0` if no arguments
are given or all arguments are ±0.



 
Description
-----------

 
Calculating the hypotenuse of a right triangle, or the magnitude of a
complex number, uses the formula `Math.sqrt(v1*v1 + v2*v2)`, where v1
and v2 are the lengths of the triangle\'s legs, or the complex number\'s
real and complex components. The corresponding distance in 2 or more
dimensions can be calculated by adding more squares under the square
root: `Math.sqrt(v1*v1 + v2*v2 + v3*v3 + v4*v4)`.

This function makes this calculation easier and faster; you call
`Math.hypot(v1, v2)`, or `Math.hypot(v1, /* …, */, vN)`.

`Math.hypot` also avoids overflow/underflow problems if the magnitude of
your numbers is very large. The largest number you can represent in JS
is [`Number.MAX_VALUE`](../number/max_value), which is around 10^308^.
If your numbers are larger than about 10^154^, taking the square of them
will result in Infinity. For example,
`Math.sqrt(1e200*1e200 + 1e200*1e200) = Infinity`. If you use `hypot()`
instead, you get a better answer:
`Math.hypot(1e200, 1e200) = 1.4142...e+200` . This is also true with
very small numbers. `Math.sqrt(1e-200*1e-200 + 1e-200*1e-200) = 0`, but
`Math.hypot(1e-200, 1e-200) = 1.4142...e-200`.

With one argument, `Math.hypot()` is equivalent to [`Math.abs()`](abs).
[`Math.hypot.length`](../function/length) is 2, which weakly signals
that it\'s designed to handle at least two parameters.

Because `hypot()` is a static method of `Math`, you always use it as
`Math.hypot()`, rather than as a method of a `Math` object you created
(`Math` is not a constructor).



 
Examples
--------


 
### Using Math.hypot() 

 
 
 
[js]


```js
Math.hypot(3, 4); // 5
Math.hypot(3, 4, 5); // 7.0710678118654755
Math.hypot(); // 0
Math.hypot(NaN); // NaN
Math.hypot(NaN, Infinity); // Infinity
Math.hypot(3, 4, "foo"); // NaN, since +'foo' => NaN
Math.hypot(3, 4, "5"); // 7.0710678118654755, +'5' => 5
Math.hypot(-3); // 3, the same as Math.abs(-3)
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-math.hypot]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-math.hypot)

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

`hypot`

38

12

27

25

8

38

27

25

8

3.0

38

1.0

0.12.0

 
See also 
--------

 
-   [Polyfill of `Math.hypot` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-math)
-   [`Math.abs()`](abs)
-   [`Math.pow()`](pow)
-   [`Math.sqrt()`](sqrt)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/hypot>

