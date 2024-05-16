String.prototype.charCodeAt()
=============================

 
The `charCodeAt()` method of [`String`](../string) values returns an
integer between `0` and `65535` representing the UTF-16 code unit at the
given index.

`charCodeAt()` always indexes the string as a sequence of [UTF-16 code
units](../string#utf-16_characters_unicode_code_points_and_grapheme_clusters),
so it may return lone surrogates. To get the full Unicode code point at
the given index, use [`String.prototype.codePointAt()`](codepointat).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
charCodeAt(index)
```




 
### Parameters

 

[`index`](#index)

:   Zero-based index of the character to be returned. [Converted to an
    integer](../number#integer_conversion) --- `undefined` is converted
    to 0.



 
### Return value 

 
An integer between `0` and `65535` representing the UTF-16 code unit
value of the character at the specified `index`. If `index` is out of
range of `0` -- `str.length - 1`, `charCodeAt()` returns
[`NaN`](../nan).



 
Description
-----------

 
Characters in a string are indexed from left to right. The index of the
first character is `0`, and the index of the last character in a string
called `str` is `str.length - 1`.

Unicode code points range from `0` to `1114111` (`0x10FFFF`).
`charCodeAt()` always returns a value that is less than `65536`, because
the higher code points are represented by *a pair* of 16-bit surrogate
pseudo-characters. Therefore, in order to get a full character with
value greater than `65535`, it is necessary to retrieve not only
`charCodeAt(i)`, but also `charCodeAt(i + 1)` (as if manipulating a
string with two characters), or to use [`codePointAt(i)`](codepointat)
instead. For information on Unicode, see [UTF-16 characters, Unicode
code points, and grapheme
clusters](../string#utf-16_characters_unicode_code_points_and_grapheme_clusters).



 
Examples
--------


 
### Using charCodeAt() 

 
The following example returns `65`, the Unicode value for A.

 
 
[js]


```js
"ABC".charCodeAt(0); // returns 65
```


`charCodeAt()` may return lone surrogates, which are not valid Unicode
characters.

 
 
[js]


```js
const str = "𠮷𠮾";
console.log(str.charCodeAt(0)); // 55362, or d842, which is not a valid Unicode character
console.log(str.charCodeAt(1)); // 57271, or dfb7, which is not a valid Unicode character
```


To get the full Unicode code point at the given index, use
[`String.prototype.codePointAt()`](codepointat).

 
 
[js]


```js
const str = "𠮷𠮾";
console.log(str.codePointAt(0)); // 134071
```


 
**Note:** Avoid re-implementing `codePointAt()` using `charCodeAt()`.
The translation from UTF-16 surrogates to Unicode code points is
complex, and `codePointAt()` may be more performant as it directly uses
the internal representation of the string. Install a polyfill for
`codePointAt()` if necessary.


Below is a possible algorithm to convert a pair of UTF-16 code units
into a Unicode code point, adapted from the [Unicode
FAQ](https://unicode.org/faq/utf_bom.html#utf16-3):

 
 
[js]


```js
// constants
const LEAD_OFFSET = 0xd800 - (0x10000 >> 10);
const SURROGATE_OFFSET = 0x10000 - (0xd800 << 10) - 0xdc00;

function utf16ToUnicode(lead, trail) {
  return (lead << 10) + trail + SURROGATE_OFFSET;
}
function unicodeToUTF16(codePoint) {
  const lead = LEAD_OFFSET + (codePoint >> 10);
  const trail = 0xdc00 + (codePoint & 0x3ff);
  return [lead, trail];
}

const str = "𠮷";
console.log(utf16ToUnicode(str.charCodeAt(0), str.charCodeAt(1))); // 134071
console.log(str.codePointAt(0)); // 134071
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-string.prototype.charcodeat]](https://tc39.es/ecma262/multipage/text-processing.html#sec-string.prototype.charcodeat)

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

`charCodeAt`

1

12

1

4

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

 
See also 
--------

 
-   [`String.fromCharCode()`](fromcharcode)
-   [`String.prototype.charAt()`](charat)
-   [`String.fromCodePoint()`](fromcodepoint)
-   [`String.prototype.codePointAt()`](codepointat)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/charCodeAt>

