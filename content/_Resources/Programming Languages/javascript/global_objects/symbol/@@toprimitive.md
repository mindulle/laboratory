Symbol.prototype\[@\@toPrimitive\]()
====================================

 
The `[@@toPrimitive]()` method of [`Symbol`](../symbol) values returns
this symbol value.


 
Syntax
------

 
 
 
[js]


```js
symbolValue[Symbol.toPrimitive](hint)
```




 
### Parameters

 

[`hint`](#hint)

:   A string value indicating the primitive value to return. The value
    is ignored.



 
### Return value 

 
The primitive value of the specified [`Symbol`](../symbol) object.



 
Description
-----------

 
The `[@@toPrimitive]()` method of [`Symbol`](../symbol) returns the
primitive value of a Symbol object as a Symbol data type. The `hint`
argument is not used.

JavaScript calls the `[@@toPrimitive]()` method to convert an object to
a primitive value. You rarely need to invoke the `[@@toPrimitive]()`
method yourself; JavaScript automatically invokes it when encountering
an object where a primitive value is expected.



 
Examples
--------


 
### Using @\@toPrimitive 

 
 
 
[js]


```js
const sym = Symbol("example");
sym === sym[Symbol.toPrimitive](); // true
```




Specifications
--------------

 
  ----------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ----------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-symbol.prototype-@\@toprimitive]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-symbol.prototype-@@toprimitive)

  ----------------------------------------------------------------------------------------------------------------------------------------------


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

`@@toPrimitive`

47

15

44

34

10

47

44

34

10

5.0

47

1.0

6.0.0

 
See also 
--------

 
-   [`Symbol.toPrimitive`](toprimitive)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/@@toPrimitive>

