Symbol.prototype.toString()
===========================

 
The `toString()` method of [`Symbol`](../symbol) values returns a string
representing this symbol value.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
toString()
```




 
### Parameters

 
None.



 
### Return value 

 
A string representing the specified symbol value.



 
Description
-----------

 
The [`Symbol`](../symbol) object overrides the `toString` method of
[`Object`](../object); it does not inherit
[`Object.prototype.toString()`](../object/tostring). For `Symbol`
values, the `toString` method returns a descriptive string in the form
`"Symbol(description)"`, where `description` is the symbol\'s
[description](description).

The `toString()` method requires its `this` value to be a `Symbol`
primitive or wrapper object. It throws a [`TypeError`](../typeerror) for
other `this` values without attempting to coerce them to symbol values.

Because `Symbol` has a [`[@@toPrimitive]()`](@@toprimitive) method, that
method always takes priority over `toString()` when a `Symbol` object is
[coerced to a string](../string#string_coercion). However, because
`Symbol.prototype[@@toPrimitive]()` returns a symbol primitive, and
symbol primitives throw a [`TypeError`](../typeerror) when implicitly
converted to a string, the `toString()` method is never implicitly
called by the language. To stringify a symbol, you must explicitly call
its `toString()` method or use the
[`String()`](../string/string#using_string_to_stringify_a_symbol)
function.



 
Examples
--------


 
### Using toString() 

 
 
 
[js]


```js
Symbol("desc").toString(); // "Symbol(desc)"

// well-known symbols
Symbol.iterator.toString(); // "Symbol(Symbol.iterator)"

// global symbols
Symbol.for("foo").toString(); // "Symbol(foo)"
```




 
### Implicitly calling toString() 

 
The only way to make JavaScript implicitly call `toString()` instead of
[`[@@toPrimitive]()`](@@toprimitive) on a symbol wrapper object is by
[deleting](../../operators/delete) the `@@toPrimitive` method first.

 
**Warning:** You should not do this in practice. Never mutate built-in
objects unless you know exactly what you\'re doing.


 
 
[js]


```js
delete Symbol.prototype[Symbol.toPrimitive];
console.log(`${Object(Symbol("foo"))}`); // "Symbol(foo)"
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-symbol.prototype.tostring]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-symbol.prototype.tostring)

  -----------------------------------------------------------------------------------------------------------------------------------


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

`toString`

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

 
-   [`Object.prototype.toString()`](../object/tostring)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/toString>

