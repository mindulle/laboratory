Symbol.toPrimitive
==================

 
The `Symbol.toPrimitive` static data property represents the [well-known
symbol](../symbol#well-known_symbols) `@@toPrimitive`. All [type
coercion](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#type_coercion)
algorithms look up this symbol on objects for the method that accepts a
preferred type and returns a primitive representation of the object,
before falling back to using the object\'s `valueOf()` and `toString()`
methods.


 
Try it 
------

 



 
Value
-----

 
The well-known symbol `@@toPrimitive`.

 
Property attributes of `Symbol.toPrimitive`




Writable

no

Enumerable

no

Configurable

no

 
Description
-----------

 
With the help of the `Symbol.toPrimitive` property (used as a function
value), an object can be converted to a primitive value. The function is
called with a string argument `hint`, which specifies the preferred type
of the result primitive value. The `hint` argument can be one of
`"number"`, `"string"`, and `"default"`.

The `"number"` hint is used by [numeric
coercion](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#numeric_coercion)
algorithms. The `"string"` hint is used by the [string
coercion](../string#string_coercion) algorithm. The `"default"` hint is
used by the [primitive
coercion](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#primitive_coercion)
algorithm. The `hint` only acts as a weak signal of preference, and the
implementation is free to ignore it (as
[`Symbol.prototype[@@toPrimitive]()`](@@toprimitive) does). The language
does not enforce alignment between the `hint` and the result type,
although `[@@toPrimitive]()` must return a primitive, or a
[`TypeError`](../typeerror) is thrown.

Objects without the `@@toPrimitive` property are converted to primitives
by calling the `valueOf()` and `toString()` methods in different orders,
which is explained in more detail in the [type
coercion](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#type_coercion)
section. `@@toPrimitive` allows full control over the primitive
conversion process. For example,
[`Date.prototype[@@toPrimitive]`](../date/@@toprimitive) treats
`"default"` as if it\'s `"string"` and calls `toString()` instead of
`valueOf()`. [`Symbol.prototype[@@toPrimitive]`](@@toprimitive) ignores
the hint and always returns a symbol, which means even in string
contexts, [`Symbol.prototype.toString()`](tostring) won\'t be called,
and `Symbol` objects must always be explicitly converted to strings
through [`String()`](../string/string).



 
Examples
--------


 
### Modifying primitive values converted from an object 

 
Following example describes how `Symbol.toPrimitive` property can modify
the primitive value converted from an object.

 
 
[js]


```js
// An object without Symbol.toPrimitive property.
const obj1 = {};
console.log(+obj1); // NaN
console.log(`${obj1}`); // "[object Object]"
console.log(obj1 + ""); // "[object Object]"

// An object with Symbol.toPrimitive property.
const obj2 = {
  [Symbol.toPrimitive](hint) {
    if (hint === "number") {
      return 10;
    }
    if (hint === "string") {
      return "hello";
    }
    return true;
  },
};
console.log(+obj2); // 10        — hint is "number"
console.log(`${obj2}`); // "hello"   — hint is "string"
console.log(obj2 + ""); // "true"    — hint is "default"
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-symbol.toprimitive]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-symbol.toprimitive)

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

`toPrimitive`

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

 
-   [Polyfill of `Symbol.toPrimitive` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-symbol)
-   [`Date.prototype[@@toPrimitive]()`](../date/@@toprimitive)
-   [`Symbol.prototype[@@toPrimitive]()`](@@toprimitive)
-   [`Object.prototype.toString()`](../object/tostring)
-   [`Object.prototype.valueOf()`](../object/valueof)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/toPrimitive>

