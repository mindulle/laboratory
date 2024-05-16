RegExp.prototype.dotAll
=======================

 
The `dotAll` accessor property of [`RegExp`](../regexp) instances
returns whether or not the `s` flag is used with this regular
expression.


 
Try it 
------

 



 
Description
-----------

 
`RegExp.prototype.dotAll` has the value `true` if the `s` flag was used;
otherwise, `false`. The `s` flag indicates that the dot special
character (`.`) should additionally match the following line terminator
(\"newline\") characters in a string, which it would not match
otherwise:

-   U+000A LINE FEED (LF) (`\n`)
-   U+000D CARRIAGE RETURN (CR) (`\r`)
-   U+2028 LINE SEPARATOR
-   U+2029 PARAGRAPH SEPARATOR

This effectively means the dot will match any character on the Unicode
Basic Multilingual Plane (BMP). To allow it to match astral characters,
the `u` (unicode) flag should be used. Using both flags in conjunction
allows the dot to match any Unicode character, without exceptions.

The set accessor of `dotAll` is `undefined`. You cannot change this
property directly.



 
Examples
--------


 
### Using dotAll 

 
 
 
[js]


```js
const str1 = "bar\nexample foo example";

const regex1 = /bar.example/s;

console.log(regex1.dotAll); // true

console.log(str1.replace(regex1, "")); // foo example

const str2 = "bar\nexample foo example";

const regex2 = /bar.example/;

console.log(regex2.dotAll); // false

console.log(str2.replace(regex2, ""));
// bar
// example foo example
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-get-regexp.prototype.dotAll]](https://tc39.es/ecma262/multipage/text-processing.html#sec-get-regexp.prototype.dotAll)

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

`dotAll`

62

79

78

49

11.1

62

79

46

11.3

8.0

62

1.0

8.10.0

 
See also 
--------

 
-   [Polyfill of the `dotAll` flag in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-string-and-regexp)
-   [`RegExp.prototype.lastIndex`](lastindex)
-   [`RegExp.prototype.global`](global)
-   [`RegExp.prototype.hasIndices`](hasindices)
-   [`RegExp.prototype.ignoreCase`](ignorecase)
-   [`RegExp.prototype.multiline`](multiline)
-   [`RegExp.prototype.source`](source)
-   [`RegExp.prototype.sticky`](sticky)
-   [`RegExp.prototype.unicode`](unicode)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/dotAll>

