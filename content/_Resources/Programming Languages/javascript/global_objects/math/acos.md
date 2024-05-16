Math.acos()
===========

 
The `Math.acos()` static method returns the inverse cosine (in radians)
of a number. That is,

$$\forall x \in \lbrack{- 1},1\rbrack,\;{\operatorname{\mathtt{M}\mathtt{a}\mathtt{t}\mathtt{h}.\mathtt{a}\mathtt{c}\mathtt{o}\mathtt{s}}(\mathtt{x})} = \arccos(x) = \text{the\ unique}y \in \lbrack 0,\pi\rbrack\text{such\ that}\cos(y) = x$$


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Math.acos(x)
```




 
### Parameters

 

[`x`](#x)

:   A number between -1 and 1, inclusive, representing the angle\'s
    cosine value.



 
### Return value 

 
The inverse cosine (angle in radians between 0 and π, inclusive) of `x`.
If `x` is less than -1 or greater than 1, returns [`NaN`](../nan).



 
Description
-----------

 
Because `acos()` is a static method of `Math`, you always use it as
`Math.acos()`, rather than as a method of a `Math` object you created
(`Math` is not a constructor).



 
Examples
--------


 
### Using Math.acos() 

 
 
 
[js]


```js
Math.acos(-2); // NaN
Math.acos(-1); // 3.141592653589793 (π)
Math.acos(0); // 1.5707963267948966 (π/2)
Math.acos(0.5); // 1.0471975511965979 (π/3)
Math.acos(1); // 0
Math.acos(2); // NaN
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-math.acos]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-math.acos)

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

`acos`

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

 
-   [`Math.asin()`](asin)
-   [`Math.atan()`](atan)
-   [`Math.atan2()`](atan2)
-   [`Math.cos()`](cos)
-   [`Math.sin()`](sin)
-   [`Math.tan()`](tan)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/acos>

