Symbol() constructor
====================

 
The `Symbol()` function returns primitive values of type Symbol.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Symbol()
Symbol(description)
```


 
**Note:** `Symbol()` can only be called without
[`new`](../../operators/new). Attempting to construct it with `new`
throws a [`TypeError`](../typeerror).




 
### Parameters

 

[`description`](#description) [Optional]

:   A string. A description of the symbol which can be used for
    debugging but not to access the symbol itself.



 
Examples
--------


 
### Creating symbols 

 
To create a new primitive symbol, you write `Symbol()` with an optional
string as its description:

 
 
[js]


```js
const sym1 = Symbol();
const sym2 = Symbol("foo");
const sym3 = Symbol("foo");
```


The above code creates three new symbols. Note that `Symbol("foo")` does
not coerce the string `"foo"` into a symbol. It creates a new symbol
each time:

 
 
[js]


```js
Symbol("foo") === Symbol("foo"); // false
```




 
### new Symbol() 

 
The following syntax with the [`new`](../../operators/new) operator will
throw a [`TypeError`](../typeerror):

 
 
[js]


```js
const sym = new Symbol(); // TypeError
```


This prevents authors from creating an explicit `Symbol` wrapper object
instead of a new symbol value and might be surprising as creating
explicit wrapper objects around primitive data types is generally
possible (for example, `new Boolean`, `new String` and `new Number`).

If you really want to create a `Symbol` wrapper object, you can use the
`Object()` function:

 
 
[js]


```js
const sym = Symbol("foo");
const symObj = Object(sym);
typeof sym; // "symbol"
typeof symObj; // "object"
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-symbol-constructor]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-symbol-constructor)

  ---------------------------------------------------------------------------------------------------------------------


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

`Symbol`

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

 
-   [Polyfill of `Symbol` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-symbol)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/Symbol>

