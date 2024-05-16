Infinity
========

 
The `Infinity` global property is a numeric value representing infinity.


 
Try it 
------

 



 
Value
-----

 
The same number value as
[`Number.POSITIVE_INFINITY`](number/positive_infinity).

 
Property attributes of `Infinity`




Writable

no

Enumerable

no

Configurable

no

 
Description
-----------

 
`Infinity` is a property of the *global object*. In other words, it is a
variable in global scope.

The value `Infinity` (positive infinity) is greater than any other
number.

This value behaves slightly differently than mathematical infinity; see
[`Number.POSITIVE_INFINITY`](number/positive_infinity) for details.



 
Examples
--------


 
### Using Infinity 

 
 
 
[js]


```js
console.log(Infinity); /* Infinity */
console.log(Infinity + 1); /* Infinity */
console.log(Math.pow(10, 1000)); /* Infinity */
console.log(Math.log(0)); /* -Infinity */
console.log(1 / Infinity); /* 0 */
console.log(1 / 0); /* Infinity */
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-value-properties-of-the-global-object-infinity]](https://tc39.es/ecma262/multipage/global-object.html#sec-value-properties-of-the-global-object-infinity)

  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------


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

`Infinity`

1

12

1

4

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

 
-   [`Number.NEGATIVE_INFINITY`](number/negative_infinity)
-   [`Number.POSITIVE_INFINITY`](number/positive_infinity)
-   [`Number.isFinite`](number/isfinite)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Infinity>

