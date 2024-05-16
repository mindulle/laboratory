Symbol.search
=============

 
The `Symbol.search` static data property represents the [well-known
symbol](../symbol#well-known_symbols) `@@search`. The
[`String.prototype.search()`](../string/search) method looks up this
symbol on its first argument for the method that returns the index
within a string that matches the current object.

For more information, see
[`RegExp.prototype[@@search]()`](../regexp/@@search) and
[`String.prototype.search()`](../string/search).


 
Try it 
------

 



 
Value
-----

 
The well-known symbol `@@search`.

 
Property attributes of `Symbol.search`




Writable

no

Enumerable

no

Configurable

no

 
Examples
--------


 
### Custom string search 

 
 
 
[js]


```js
class caseInsensitiveSearch {
  constructor(value) {
    this.value = value.toLowerCase();
  }
  [Symbol.search](string) {
    return string.toLowerCase().indexOf(this.value);
  }
}

console.log("foobar".search(new caseInsensitiveSearch("BaR"))); // 3
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-symbol.search]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-symbol.search)

  -----------------------------------------------------------------------------------------------------------


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

`search`

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

 
-   [Polyfill of `Symbol.search` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-symbol)
-   [`Symbol.match`](match)
-   [`Symbol.matchAll`](matchall)
-   [`Symbol.replace`](replace)
-   [`Symbol.split`](split)
-   [`String.prototype.search()`](../string/search)
-   [`RegExp.prototype[@@search]()`](../regexp/@@search)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/search>

