Math.sin()
==========

 
The `Math.sin()` static method returns the sine of a number in radians.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Math.sin(x)
```




 
### Parameters

 

[`x`](#x)

:   A number representing an angle in radians.



 
### Return value 

 
The sine of `x`, between -1 and 1, inclusive. If `x` is
[`Infinity`](../infinity), `-Infinity`, or [`NaN`](../nan), returns
[`NaN`](../nan).



 
Description
-----------

 
Because `sin()` is a static method of `Math`, you always use it as
`Math.sin()`, rather than as a method of a `Math` object you created
(`Math` is not a constructor).



 
Examples
--------


 
### Using Math.sin() 

 
 
 
[js]


```js
Math.sin(-Infinity); // NaN
Math.sin(-0); // -0
Math.sin(0); // 0
Math.sin(1); // 0.8414709848078965
Math.sin(Math.PI / 2); // 1
Math.sin(Infinity); // NaN
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-math.sin]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-math.sin)

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

`sin`

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
-   [`Math.cos()`](cos)
-   [`Math.tan()`](tan)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/sin>

