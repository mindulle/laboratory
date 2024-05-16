Object.getOwnPropertySymbols()
==============================

 
The `Object.getOwnPropertySymbols()` static method returns an array of
all symbol properties found directly upon a given object.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Object.getOwnPropertySymbols(obj)
```




 
### Parameters

 

[`obj`](#obj)

:   The object whose symbol properties are to be returned.



 
### Return value 

 
An array of all symbol properties found directly upon the given object.



 
Description
-----------

 
Similar to [`Object.getOwnPropertyNames()`](getownpropertynames), you
can get all symbol properties of a given object as an array of symbols.
Note that [`Object.getOwnPropertyNames()`](getownpropertynames) itself
does not contain the symbol properties of an object and only the string
properties.

As all objects have no own symbol properties initially,
`Object.getOwnPropertySymbols()` returns an empty array unless you have
set symbol properties on your object.



 
Examples
--------


 
### Using Object.getOwnPropertySymbols() 

 
 
 
[js]


```js
const obj = {};
const a = Symbol("a");
const b = Symbol.for("b");

obj[a] = "localSymbol";
obj[b] = "globalSymbol";

const objectSymbols = Object.getOwnPropertySymbols(obj);

console.log(objectSymbols.length); // 2
console.log(objectSymbols); // [Symbol(a), Symbol(b)]
console.log(objectSymbols[0]); // Symbol(a)
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-object.getownpropertysymbols]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-object.getownpropertysymbols)

  -----------------------------------------------------------------------------------------------------------------------------------------


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

`getOwnPropertySymbols`

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

 
-   [Polyfill of `Object.getOwnPropertySymbols` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-symbol)
-   [`Object.getOwnPropertyNames()`](getownpropertynames)
-   [`Symbol`](../symbol)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/getOwnPropertySymbols>

