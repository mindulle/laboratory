Symbol.split
============

 
The `Symbol.split` static data property represents the [well-known
symbol](../symbol#well-known_symbols) `@@split`. The
[`String.prototype.split()`](../string/split) method looks up this
symbol on its first argument for the method that splits a string at the
indices that match the current object.

For more information,
see[`RegExp.prototype[@@split]()`](../regexp/@@split) and
[`String.prototype.split()`](../string/split).


 
Try it 
------

 



 
Value
-----

 
The well-known symbol `@@split`.

 
Property attributes of `Symbol.split`




Writable

no

Enumerable

no

Configurable

no

 
Examples
--------


 
### Custom reverse split 

 
 
 
[js]


```js
class ReverseSplit {
  [Symbol.split](string) {
    const array = string.split(" ");
    return array.reverse();
  }
}

console.log("Another one bites the dust".split(new ReverseSplit()));
// [ "dust", "the", "bites", "one", "Another" ]
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-symbol.split]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-symbol.split)

  ---------------------------------------------------------------------------------------------------------


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

`split`

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

 
-   [Polyfill of `Symbol.split` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-symbol)
-   [`Symbol.match`](match)
-   [`Symbol.matchAll`](matchall)
-   [`Symbol.replace`](replace)
-   [`Symbol.search`](search)
-   [`String.prototype.split()`](../string/split)
-   [`RegExp.prototype[@@split]()`](../regexp/@@split)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/split>

