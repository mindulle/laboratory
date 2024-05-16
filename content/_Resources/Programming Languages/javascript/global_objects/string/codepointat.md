String.prototype.codePointAt()
==============================

 
The `codePointAt()` method of [`String`](../string) values returns a
non-negative integer that is the Unicode code point value of the
character starting at the given index. Note that the index is still
based on UTF-16 code units, not Unicode code points.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
codePointAt(index)
```




 
### Parameters

 

[`index`](#index)

:   Zero-based index of the character to be returned. [Converted to an
    integer](../number#integer_conversion) --- `undefined` is converted
    to 0.



 
### Return value 

 
A non-negative integer representing the code point value of the
character at the given `index`.

-   If `index` is out of the range of `0` -- `str.length - 1`,
    `codePointAt()` returns [`undefined`](../undefined).
-   If the element at `index` is a UTF-16 leading surrogate, returns the
    code point of the surrogate *pair*.
-   If the element at `index` is a UTF-16 trailing surrogate, returns
    *only* the trailing surrogate code unit.



 
Description
-----------

 
Characters in a string are indexed from left to right. The index of the
first character is `0`, and the index of the last character in a string
called `str` is `str.length - 1`.

Unicode code points range from `0` to `1114111` (`0x10FFFF`). In UTF-16,
each string index is a code unit with value `0` -- `65535`. Higher code
points are represented by *a pair* of 16-bit surrogate
pseudo-characters. Therefore, `codePointAt()` returns a code point that
may span two string indices. For information on Unicode, see [UTF-16
characters, Unicode code points, and grapheme
clusters](../string#utf-16_characters_unicode_code_points_and_grapheme_clusters).



 
Examples
--------


 
### Using codePointAt() 

 
 
 
[js]


```js
"ABC".codePointAt(0); // 65
"ABC".codePointAt(0).toString(16); // 41

"😍".codePointAt(0); // 128525
"\ud83d\ude0d".codePointAt(0); // 128525
"\ud83d\ude0d".codePointAt(0).toString(16); // 1f60d

"😍".codePointAt(1); // 56845
"\ud83d\ude0d".codePointAt(1); // 56845
"\ud83d\ude0d".codePointAt(1).toString(16); // de0d

"ABC".codePointAt(42); // undefined
```




 
### Looping with codePointAt() 

 
Because using string indices for looping causes the same code point to
be visited twice (once for the leading surrogate, once for the trailing
surrogate), and the second time `codePointAt()` returns *only* the
trailing surrogate, it\'s better to avoid looping by index.

 
 
[js]


```js
const str = "\ud83d\udc0e\ud83d\udc71\u2764";

for (let i = 0; i < str.length; i++) {
  console.log(str.codePointAt(i).toString(16));
}
// '1f40e', 'dc0e', '1f471', 'dc71', '2764'
```


Instead, use a
[`for...of`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration#for...of_statement)
statement or [spread the string](../../operators/spread_syntax), both of
which invoke the string\'s [`@@iterator`](@@iterator), which iterates by
code points. Then, use `codePointAt(0)` to get the code point of each
element.

 
 
[js]


```js
for (const codePoint of str) {
  console.log(codePoint.codePointAt(0).toString(16));
}
// '1f40e', '1f471', '2764'

[...str].map((cp) => cp.codePointAt(0).toString(16));
// ['1f40e', '1f471', '2764']
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-string.prototype.codepointat]](https://tc39.es/ecma262/multipage/text-processing.html#sec-string.prototype.codepointat)

  -------------------------------------------------------------------------------------------------------------------------------------


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

`codePointAt`

41

12

29

28

9

41

29

28

9

4.0

41

1.0

4.0.0

 
See also 
--------

 
-   [Polyfill of `String.prototype.codePointAt` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-string-and-regexp)
-   [`String.fromCodePoint()`](fromcodepoint)
-   [`String.fromCharCode()`](fromcharcode)
-   [`String.prototype.charCodeAt()`](charcodeat)
-   [`String.prototype.charAt()`](charat)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/codePointAt>

