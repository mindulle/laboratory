Symbol.match
============

 
The `Symbol.match` static data property represents the [well-known
symbol](../symbol#well-known_symbols) `@@match`. The
[`String.prototype.match()`](../string/match) method looks up this
symbol on its first argument for the method used to match an input
string against the current object. This symbol is also used to determine
if an object should be [treated as a
regex](../regexp#special_handling_for_regexes).

For more information, see
[`RegExp.prototype[@@match]()`](../regexp/@@match) and
[`String.prototype.match()`](../string/match).


 
Try it 
------

 



 
Value
-----

 
The well-known symbol `@@match`.

 
Property attributes of `Symbol.match`




Writable

no

Enumerable

no

Configurable

no

 
Description
-----------

 
This function is also used to identify [if objects have the behavior of
regular expressions](../regexp#special_handling_for_regexes). For
example, the methods
[`String.prototype.startsWith()`](../string/startswith),
[`String.prototype.endsWith()`](../string/endswith) and
[`String.prototype.includes()`](../string/includes), check if their
first argument is a regular expression and will throw a
[`TypeError`](../typeerror) if they are. Now, if the `match` symbol is
set to `false` (or a
[Falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy) value
except `undefined`), it indicates that the object is not intended to be
used as a regular expression object.



 
Examples
--------


 
### Marking a RegExp as not a regex 

 
The following code will throw a [`TypeError`](../typeerror):

 
 
[js]


```js
"/bar/".startsWith(/bar/);

// Throws TypeError, as /bar/ is a regular expression
// and Symbol.match is not modified.
```


However, if you set `Symbol.match` to `false`, the object will be
considered as [not a regular expression
object](../regexp#special_handling_for_regexes). The methods
`startsWith` and `endsWith` won\'t throw a `TypeError` as a consequence.

 
 
[js]


```js
const re = /foo/;
re[Symbol.match] = false;
"/foo/".startsWith(re); // true
"/baz/".endsWith(re); // false
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-symbol.match]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-symbol.match)

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

`match`

50

79

40

37

10

50

40

37

10

5.0

50

1.0

6.0.0

 
See also 
--------

 
-   [Polyfill of `Symbol.match` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-symbol)
-   [`Symbol.matchAll`](matchall)
-   [`Symbol.replace`](replace)
-   [`Symbol.search`](search)
-   [`Symbol.split`](split)
-   [`String.prototype.match()`](../string/match)
-   [`RegExp.prototype[@@match]()`](../regexp/@@match)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/match>

