Math.PI
=======

 
The `Math.PI` static data property represents the ratio of the
circumference of a circle to its diameter, approximately 3.14159.


 
Try it 
------

 



 
Value
-----

 
$${\mathtt{M}\mathtt{a}\mathtt{t}\mathtt{h}.\mathtt{P}\mathtt{I}} = \pi \approx 3.14159$$

 
Property attributes of `Math.PI`




Writable

no

Enumerable

no

Configurable

no

 
Description
-----------

 
Because `PI` is a static property of `Math`, you always use it as
`Math.PI`, rather than as a property of a `Math` object you created
(`Math` is not a constructor).



 
Examples
--------


 
### Using Math.PI 

 
The following function uses `Math.PI` to calculate the circumference of
a circle with a passed radius.

 
 
[js]


```js
function calculateCircumference(radius) {
  return Math.PI * (radius + radius);
}

calculateCircumference(1); // 6.283185307179586
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-math.pi]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-math.pi)

  ---------------------------------------------------------------------------------------------


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

`PI`

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

 
-   [`Math`](../math)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/PI>

