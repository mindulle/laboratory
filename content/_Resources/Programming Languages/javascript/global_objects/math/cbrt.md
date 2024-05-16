Math.cbrt()
===========

 
The `Math.cbrt()` static method returns the cube root of a number. That
is

$${\operatorname{\mathtt{M}\mathtt{a}\mathtt{t}\mathtt{h}.\mathtt{c}\mathtt{b}\mathtt{r}\mathtt{t}}(\mathtt{x})} = \sqrt[3]{x} = \text{the\ unique}y\text{such\ that}y^{3} = x$$


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Math.cbrt(x)
```




 
### Parameters

 

[`x`](#x)

:   A number.



 
### Return value 

 
The cube root of `x`.



 
Description
-----------

 
Because `cbrt()` is a static method of `Math`, you always use it as
`Math.cbrt()`, rather than as a method of a `Math` object you created
(`Math` is not a constructor).



 
Examples
--------


 
### Using Math.cbrt() 

 
 
 
[js]


```js
Math.cbrt(-Infinity); // -Infinity
Math.cbrt(-1); // -1
Math.cbrt(-0); // -0
Math.cbrt(0); // 0
Math.cbrt(1); // 1
Math.cbrt(2); // 1.2599210498948732
Math.cbrt(Infinity); // Infinity
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-math.cbrt]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-math.cbrt)

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

`cbrt`

38

12

25

25

8

38

25

25

8

3.0

38

1.0

0.12.0

 
See also 
--------

 
-   [Polyfill of `Math.cbrt` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-math)
-   [`Math.pow()`](pow)
-   [`Math.sqrt()`](sqrt)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/cbrt>

