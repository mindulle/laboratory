Math.cos()
==========

 
The `Math.cos()` static method returns the cosine of a number in
radians.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Math.cos(x)
```




 
### Parameters

 

[`x`](#x)

:   A number representing an angle in radians.



 
### Return value 

 
The cosine of `x`, between -1 and 1, inclusive. If `x` is
[`Infinity`](../infinity), `-Infinity`, or [`NaN`](../nan), returns
[`NaN`](../nan).



 
Description
-----------

 
Because `cos()` is a static method of `Math`, you always use it as
`Math.cos()`, rather than as a method of a `Math` object you created
(`Math` is not a constructor).



 
Examples
--------


 
### Using Math.cos() 

 
 
 
[js]


```js
Math.cos(-Infinity); // NaN
Math.cos(-0); // 1
Math.cos(0); // 1
Math.cos(1); // 0.5403023058681398
Math.cos(Math.PI); // -1
Math.cos(2 * Math.PI); // 1
Math.cos(Infinity); // NaN
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-math.cos]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-math.cos)

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

`cos`

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

 
-   [`Math.acos()`](acos)
-   [`Math.asin()`](asin)
-   [`Math.atan()`](atan)
-   [`Math.atan2()`](atan2)
-   [`Math.sin()`](sin)
-   [`Math.tan()`](tan)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/cos>

