Math.abs()
==========

 
The `Math.abs()` static method returns the absolute value of a number.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Math.abs(x)
```




 
### Parameters

 

[`x`](#x)

:   A number.



 
### Return value 

 
The absolute value of `x`. If `x` is negative (including `-0`), returns
`-x`. Otherwise, returns `x`. The result is therefore always a positive
number or `0`.



 
Description
-----------

 
Because `abs()` is a static method of `Math`, you always use it as
`Math.abs()`, rather than as a method of a `Math` object you created
(`Math` is not a constructor).



 
Examples
--------


 
### Using Math.abs() 

 
 
 
[js]


```js
Math.abs(-Infinity); // Infinity
Math.abs(-1); // 1
Math.abs(-0); // 0
Math.abs(0); // 0
Math.abs(1); // 1
Math.abs(Infinity); // Infinity
```




 
### Coercion of parameter 

 
`Math.abs()` [coerces its parameter to a
number](../number#number_coercion). Non-coercible values will become
`NaN`, making `Math.abs()` also return `NaN`.

 
 
[js]


```js
Math.abs("-1"); // 1
Math.abs(-2); // 2
Math.abs(null); // 0
Math.abs(""); // 0
Math.abs([]); // 0
Math.abs([2]); // 2
Math.abs([1, 2]); // NaN
Math.abs({}); // NaN
Math.abs("string"); // NaN
Math.abs(); // NaN
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-math.abs]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-math.abs)

  -----------------------------------------------------------------------------------------------


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

`abs`

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

 
-   [`Math.ceil()`](ceil)
-   [`Math.floor()`](floor)
-   [`Math.round()`](round)
-   [`Math.sign()`](sign)
-   [`Math.trunc()`](trunc)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/abs>

