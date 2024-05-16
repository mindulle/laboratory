Math.sqrt()
===========

 
The `Math.sqrt()` static method returns the square root of a number.
That is

$$\forall x \geq 0,\;{\operatorname{\mathtt{M}\mathtt{a}\mathtt{t}\mathtt{h}.\mathtt{s}\mathtt{q}\mathtt{r}\mathtt{t}}(\mathtt{x})} = \sqrt{x} = \text{the\ unique}y \geq 0\text{such\ that}y^{2} = x$$


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Math.sqrt(x)
```




 
### Parameters

 

[`x`](#x)

:   A number greater than or equal to 0.



 
### Return value 

 
The square root of `x`, a nonnegative number. If `x < 0`, returns
[`NaN`](../nan).



 
Description
-----------

 
Because `sqrt()` is a static method of `Math`, you always use it as
`Math.sqrt()`, rather than as a method of a `Math` object you created
(`Math` is not a constructor).



 
Examples
--------


 
### Using Math.sqrt() 

 
 
 
[js]


```js
Math.sqrt(-1); // NaN
Math.sqrt(-0); // -0
Math.sqrt(0); // 0
Math.sqrt(1); // 1
Math.sqrt(2); // 1.414213562373095
Math.sqrt(9); // 3
Math.sqrt(Infinity); // Infinity
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-math.sqrt]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-math.sqrt)

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

`sqrt`

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

 
-   [`Math.cbrt()`](cbrt)
-   [`Math.exp()`](exp)
-   [`Math.log()`](log)
-   [`Math.pow()`](pow)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/sqrt>

