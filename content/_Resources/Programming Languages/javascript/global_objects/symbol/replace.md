Symbol.replace
==============

 
The `Symbol.replace` static data property represents the [well-known
symbol](../symbol#well-known_symbols) `@@replace`. The
[`String.prototype.replace()`](../string/replace) method looks up this
symbol on its first argument for the method that replaces substrings
matched by the current object.

For more information, see
[`RegExp.prototype[@@replace]()`](../regexp/@@replace) and
[`String.prototype.replace()`](../string/replace).


 
Try it 
------

 



 
Value
-----

 
The well-known symbol `@@replace`.

 
Property attributes of `Symbol.replace`




Writable

no

Enumerable

no

Configurable

no

 
Examples
--------


 
### Using Symbol.replace 

 
 
 
[js]


```js
class CustomReplacer {
  constructor(value) {
    this.value = value;
  }
  [Symbol.replace](string) {
    return string.replace(this.value, "#!@?");
  }
}

console.log("football".replace(new CustomReplacer("foo"))); // "#!@?tball"
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-symbol.replace]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-symbol.replace)

  -------------------------------------------------------------------------------------------------------------


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

`replace`

50

79

49

37

10

50

49

37

10

5.0

50

1.0

6.0.0

 
See also 
--------

 
-   [Polyfill of `Symbol.replace` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-symbol)
-   [`Symbol.match`](match)
-   [`Symbol.matchAll`](matchall)
-   [`Symbol.search`](search)
-   [`Symbol.split`](split)
-   [`String.prototype.replace()`](../string/replace)
-   [`RegExp.prototype[@@replace]()`](../regexp/@@replace)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/replace>

