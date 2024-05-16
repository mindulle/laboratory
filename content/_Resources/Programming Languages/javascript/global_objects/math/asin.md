Math.asin()
===========

 
The `Math.asin()` static method returns the inverse sine (in radians) of
a number. That is,

$$\forall x \in \lbrack{- 1},1\rbrack,\;{\operatorname{\mathtt{M}\mathtt{a}\mathtt{t}\mathtt{h}.\mathtt{a}\mathtt{s}\mathtt{i}\mathtt{n}}(\mathtt{x})} = \arcsin(x) = \text{the\ unique}y \in \left\lbrack {- \frac{\pi}{2},\frac{\pi}{2}} \right\rbrack\text{such\ that}\sin(y) = x$$


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Math.asin(x)
```




 
### Parameters

 

[`x`](#x)

:   A number between -1 and 1, inclusive, representing the angle\'s sine
    value.



 
### Return value 

 
The inverse sine (angle in radians between $- \frac{\pi}{2}$ and
$\frac{\pi}{2}$, inclusive) of `x`. If `x` is less than -1 or greater
than 1, returns [`NaN`](../nan).



 
Description
-----------

 
Because `asin()` is a static method of `Math`, you always use it as
`Math.asin()`, rather than as a method of a `Math` object you created
(`Math` is not a constructor).



 
Examples
--------


 
### Using Math.asin() 

 
 
 
[js]


```js
Math.asin(-2); // NaN
Math.asin(-1); // -1.5707963267948966 (-π/2)
Math.asin(-0); // -0
Math.asin(0); // 0
Math.asin(0.5); // 0.5235987755982989 (π/6)
Math.asin(1); // 1.5707963267948966 (π/2)
Math.asin(2); // NaN
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-math.asin]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-math.asin)

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

`asin`

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
-   [`Math.atan()`](atan)
-   [`Math.atan2()`](atan2)
-   [`Math.cos()`](cos)
-   [`Math.sin()`](sin)
-   [`Math.tan()`](tan)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/asin>

