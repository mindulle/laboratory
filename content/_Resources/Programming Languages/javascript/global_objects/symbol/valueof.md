Symbol.prototype.valueOf()
==========================

 
The `valueOf()` method of [`Symbol`](../symbol) values returns this
symbol value.


 
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

 
The primitive value of the specified [`Symbol`](../symbol) object.



 
Description
-----------

 
The `valueOf()` method of [`Symbol`](../symbol) returns the primitive
value of a Symbol object as a Symbol data type.

JavaScript calls the `valueOf()` method to convert an object to a
primitive value. You rarely need to invoke the `valueOf()` method
yourself; JavaScript automatically invokes it when encountering an
object where a primitive value is expected.



 
Examples
--------


 
### Using valueOf() 

 
 
 
[js]


```js
const sym = Symbol("example");
sym === sym.valueOf(); // true
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-symbol.prototype.valueof]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-symbol.prototype.valueof)

  ---------------------------------------------------------------------------------------------------------------------------------


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

38

12

36

25

9

38

36

25

9

3.0

38

1.0

0.12.0

 
See also 
--------

 
-   [`Object.prototype.valueOf()`](../object/valueof)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/valueOf>

