Math.atan()
===========

 
The `Math.atan()` static method returns the inverse tangent (in radians)
of a number, that is

$${\operatorname{\mathtt{M}\mathtt{a}\mathtt{t}\mathtt{h}.\mathtt{a}\mathtt{t}\mathtt{a}\mathtt{n}}(\mathtt{x})} = \arctan(x) = \text{the\ unique}y \in \left\lbrack {- \frac{\pi}{2},\frac{\pi}{2}} \right\rbrack\text{such\ that}\tan(y) = x$$


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Math.atan(x)
```




 
### Parameters

 

[`x`](#x)

:   A number.



 
### Return value 

 
The inverse tangent (angle in radians between $- \frac{\pi}{2}$ and
$\frac{\pi}{2}$, inclusive) of `x`. If `x` is [`Infinity`](../infinity),
it returns $\frac{\pi}{2}$. If `x` is `-Infinity`, it returns
$- \frac{\pi}{2}$.



 
Description
-----------

 
Because `atan()` is a static method of `Math`, you always use it as
`Math.atan()`, rather than as a method of a `Math` object you created
(`Math` is not a constructor).



 
Examples
--------


 
### Using Math.atan() 

 
 
 
[js]


```js
Math.atan(-Infinity); // -1.5707963267948966 (-π/2)
Math.atan(-0); // -0
Math.atan(0); // 0
Math.atan(1); // 0.7853981633974483  (π/4)
Math.atan(Infinity); // 1.5707963267948966  (π/2)

// The angle that the line (0,0) -- (x,y) forms with the x-axis in a Cartesian coordinate system
const theta = (x, y) => Math.atan(y / x);
```


Note that you may want to avoid the `theta` function and use
[`Math.atan2()`](atan2) instead, which has a wider range (between -π and
π) and avoids outputting `NaN` for cases such as when `x` is `0`.



Specifications
--------------

 
  -------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-math.atan]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-math.atan)

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

`atan`

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
-   [`Math.atan2()`](atan2)
-   [`Math.cos()`](cos)
-   [`Math.sin()`](sin)
-   [`Math.tan()`](tan)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/atan>

