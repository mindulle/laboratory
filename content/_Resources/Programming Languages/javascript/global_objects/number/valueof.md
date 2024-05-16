Number.prototype.valueOf()
==========================

 
The `valueOf()` method of [`Number`](../number) values returns the value
of this number.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
valueOf()
```




 
### Parameters

 
None.



 
### Return value 

 
A number representing the primitive value of the specified
[`Number`](../number) object.



 
Description
-----------

 
This method is usually called internally by JavaScript and not
explicitly in web code.



 
Examples
--------


 
### Using valueOf 

 
 
 
[js]


```js
const numObj = new Number(10);
console.log(typeof numObj); // object

const num = numObj.valueOf();
console.log(num); // 10
console.log(typeof num); // number
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-number.prototype.valueof]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-number.prototype.valueof)

  -------------------------------------------------------------------------------------------------------------------------------


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

`valueOf`

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

 
-   [`Object.prototype.valueOf()`](../object/valueof)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/valueOf>

