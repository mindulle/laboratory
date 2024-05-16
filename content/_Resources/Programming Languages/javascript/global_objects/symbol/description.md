Symbol.prototype.description
============================

 
The `description` accessor property of [`Symbol`](../symbol) values
returns a string containing the description of this symbol, or
`undefined` if the symbol has no description.


 
Try it 
------

 



 
Description
-----------

 
[`Symbol`](../symbol) objects can be created with an optional
description which can be used for debugging but not to access the symbol
itself. The `Symbol.prototype.description` property can be used to read
that description. It is different to `Symbol.prototype.toString()` as it
does not contain the enclosing `"Symbol()"` string. See the examples.



 
Examples
--------


 
### Using description 

 
 
 
[js]


```js
Symbol("desc").toString(); // "Symbol(desc)"
Symbol("desc").description; // "desc"
Symbol("").description; // ""
Symbol().description; // undefined

// well-known symbols
Symbol.iterator.toString(); // "Symbol(Symbol.iterator)"
Symbol.iterator.description; // "Symbol.iterator"

// global symbols
Symbol.for("foo").toString(); // "Symbol(foo)"
Symbol.for("foo").description; // "foo"
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-symbol.prototype.description]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-symbol.prototype.description)

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

`description`

70

79

63

57

12.1

12No support for an undefined description.

70

63

49

12.2

12No support for an undefined description.

10.0

70

1.0

11.0.0

 
See also 
--------

 
-   [Polyfill of `Symbol.prototype.description` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-symbol)
-   [`Symbol.prototype.toString()`](tostring)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/description>

