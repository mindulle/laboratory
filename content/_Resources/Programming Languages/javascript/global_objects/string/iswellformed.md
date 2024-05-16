String.prototype.isWellFormed()
===============================

 
The `isWellFormed()` method of [`String`](../string) values returns a
boolean indicating whether this string contains any [lone
surrogates](../string#utf-16_characters_unicode_code_points_and_grapheme_clusters).


 
Syntax
------

 
 
 
[js]


```js
isWellFormed()
```




 
### Parameters

 
None.



 
### Return value 

 
Returns `true` if this string does not contain any lone surrogates,
`false` otherwise.



 
Description
-----------

 
Strings in JavaScript are UTF-16 encoded. UTF-16 encoding has the
concept of *surrogate pairs*, which is introduced in detail in the
[UTF-16 characters, Unicode code points, and grapheme
clusters](../string#utf-16_characters_unicode_code_points_and_grapheme_clusters)
section.

`isWellFormed()` allows you to test whether a string is well-formed
(i.e. does not contain any lone surrogates). Compared to a custom
implementation, `isWellFormed()` is more efficient, as engines can
directly access the internal representation of strings. If you need to
convert a string to a well-formed string, use the
[`toWellFormed()`](towellformed) method. `isWellFormed()` allows you to
handle ill-formed strings differently from well-formed strings, such as
throwing an error or marking it as invalid.



 
Examples
--------


 
### Using isWellFormed() 

 
 
 
[js]


```js
const strings = [
  // Lone leading surrogate
  "ab\uD800",
  "ab\uD800c",
  // Lone trailing surrogate
  "\uDFFFab",
  "c\uDFFFab",
  // Well-formed
  "abc",
  "ab\uD83D\uDE04c",
];

for (const str of strings) {
  console.log(str.isWellFormed());
}
// Logs:
// false
// false
// false
// false
// true
// true
```




 
### Avoiding errors in encodeURI() 

 
[`encodeURI`](../encodeuri) throws an error if the string passed is not
well-formed. This can be avoided by using `isWellFormed()` to test the
string before passing it to `encodeURI()`.

 
 
[js]


```js
const illFormed = "https://example.com/search?q=\uD800";

try {
  encodeURI(illFormed);
} catch (e) {
  console.log(e); // URIError: URI malformed
}

if (illFormed.isWellFormed()) {
  console.log(encodeURI(illFormed));
} else {
  console.warn("Ill-formed strings encountered."); // Ill-formed strings encountered.
}
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-string.prototype.iswellformed]](https://tc39.es/ecma262/multipage/text-processing.html#sec-string.prototype.iswellformed)

  ---------------------------------------------------------------------------------------------------------------------------------------


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

`isWellFormed`

111

111

119

97

16.4

111

119

75

16.4

22.0

111

1.32

20.0.0

 
See also 
--------

 
-   [Polyfill of `String.prototype.isWellFormed` in
    `core-js`](https://github.com/zloirock/core-js#well-formed-unicode-strings)
-   [`String.prototype.toWellFormed()`](towellformed)
-   [`String.prototype.normalize()`](normalize)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/isWellFormed>

