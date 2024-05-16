String.prototype.toWellFormed()
===============================

 
The `toWellFormed()` method of [`String`](../string) values returns a
string where all [lone
surrogates](../string#utf-16_characters_unicode_code_points_and_grapheme_clusters)
of this string are replaced with the Unicode replacement character
U+FFFD.


 
Syntax
------

 
 
 
[js]


```js
toWellFormed()
```




 
### Parameters

 
None.



 
### Return value 

 
A new string that is a copy of this string, with all lone surrogates
replaced with the Unicode replacement character U+FFFD. If `str` [is
well formed](iswellformed), a new string is still returned (essentially
a copy of `str`).



 
Description
-----------

 
Strings in JavaScript are UTF-16 encoded. UTF-16 encoding has the
concept of *surrogate pairs*, which is introduced in detail in the
[UTF-16 characters, Unicode code points, and grapheme
clusters](../string#utf-16_characters_unicode_code_points_and_grapheme_clusters)
section.

`toWellFormed()` iterates through the code units of this string, and
replaces any lone surrogates with the [Unicode replacement
character](https://en.wikipedia.org/wiki/Specials_(Unicode_block)#Replacement_character)
U+FFFD `�`. This ensures that the returned string is well-formed and can
be used in functions that expect well-formed strings, such as
[`encodeURI`](../encodeuri). Compared to a custom implementation,
`toWellFormed()` is more efficient, as engines can directly access the
internal representation of strings.

When ill-formed strings are used in certain contexts, such as
[`TextEncoder`](https://developer.mozilla.org/en-US/docs/Web/API/TextEncoder),
they are automatically converted to well-formed strings using the same
replacement character. When lone surrogates are rendered, they are also
rendered as the replacement character (a diamond with a question mark
inside).



 
Examples
--------


 
### Using toWellFormed() 

 
 
 
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
  console.log(str.toWellFormed());
}
// Logs:
// "ab�"
// "ab�c"
// "�ab"
// "c�ab"
// "abc"
// "ab😄c"
```




 
### Avoiding errors in encodeURI() 

 
[`encodeURI`](../encodeuri) throws an error if the string passed is not
well-formed. This can be avoided by using `toWellFormed()` to convert
the string to a well-formed string first.

 
 
[js]


```js
const illFormed = "https://example.com/search?q=\uD800";

try {
  encodeURI(illFormed);
} catch (e) {
  console.log(e); // URIError: URI malformed
}

console.log(encodeURI(illFormed.toWellFormed())); // "https://example.com/search?q=%EF%BF%BD"
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-string.prototype.towellformed]](https://tc39.es/ecma262/multipage/text-processing.html#sec-string.prototype.towellformed)

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

`toWellFormed`

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

 
-   [Polyfill of `String.prototype.toWellFormed` in
    `core-js`](https://github.com/zloirock/core-js#well-formed-unicode-strings)
-   [`String.prototype.isWellFormed()`](iswellformed)
-   [`String.prototype.normalize()`](normalize)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/toWellFormed>

