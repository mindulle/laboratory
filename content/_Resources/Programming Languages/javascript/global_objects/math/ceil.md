Math.ceil()
===========

 
The `Math.ceil()` static method always rounds up and returns the
smallest integer greater than or equal to a given number.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Math.ceil(x)
```




 
### Parameters

 

[`x`](#x)

:   A number.



 
### Return value 

 
The smallest integer greater than or equal to `x`. It\'s the same value
as [`-Math.floor(-x)`](floor).



 
Description
-----------

 
Because `ceil()` is a static method of `Math`, you always use it as
`Math.ceil()`, rather than as a method of a `Math` object you created
(`Math` is not a constructor).



 
Examples
--------


 
### Using Math.ceil() 

 
 
 
[js]


```js
Math.ceil(-Infinity); // -Infinity
Math.ceil(-7.004); // -7
Math.ceil(-4); // -4
Math.ceil(-0.95); // -0
Math.ceil(-0); // -0
Math.ceil(0); // 0
Math.ceil(0.95); // 1
Math.ceil(4); // 4
Math.ceil(7.004); // 8
Math.ceil(Infinity); // Infinity
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-math.ceil]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-math.ceil)

  -------------------------------------------------------------------------------------------------


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

`ceil`

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
-   [`Math.floor()`](floor)
-   [`Math.round()`](round)
-   [`Math.sign()`](sign)
-   [`Math.trunc()`](trunc)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/ceil>

