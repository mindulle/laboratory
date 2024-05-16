Symbol.matchAll
===============

 
The `Symbol.matchAll` static data property represents the [well-known
symbol](../symbol#well-known_symbols) `@@matchAll`. The
[`String.prototype.matchAll()`](../string/matchall) method looks up this
symbol on its first argument for the method that returns an iterator,
that yields matches of the current object against a string.

For more information, see
[`RegExp.prototype[@@matchAll]()`](../regexp/@@matchall) and
[`String.prototype.matchAll()`](../string/matchall).


 
Try it 
------

 



 
Value
-----

 
The well-known symbol `@@matchAll`.

 
Property attributes of `Symbol.matchAll`




Writable

no

Enumerable

no

Configurable

no

 
Examples
--------


 
### Using Symbol.matchAll 

 
 
 
[js]


```js
const str = "2016-01-02|2019-03-07";

const numbers = {
  *[Symbol.matchAll](str) {
    for (const n of str.matchAll(/[0-9]+/g)) yield n[0];
  },
};

console.log(Array.from(str.matchAll(numbers)));
// ["2016", "01", "02", "2019", "03", "07"]
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-symbol.matchall]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-symbol.matchall)

  ---------------------------------------------------------------------------------------------------------------


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

`matchAll`

73

79

67

60

13

73

67

52

13

11.0

73

1.0

12.0.0

 
See also 
--------

 
-   [Polyfill of `Symbol.matchAll` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-symbol)
-   [`Symbol.match`](match)
-   [`Symbol.replace`](replace)
-   [`Symbol.search`](search)
-   [`Symbol.split`](split)
-   [`String.prototype.matchAll()`](../string/matchall)
-   [`RegExp.prototype[@@matchAll]()`](../regexp/@@matchall)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/matchAll>

