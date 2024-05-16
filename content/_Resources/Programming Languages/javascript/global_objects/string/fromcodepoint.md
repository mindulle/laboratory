String.fromCodePoint()
======================

 
The `String.fromCodePoint()` static method returns a string created from
the specified sequence of code points.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
String.fromCodePoint()
String.fromCodePoint(num1)
String.fromCodePoint(num1, num2)
String.fromCodePoint(num1, num2, /* …, */ numN)
```




 
### Parameters

 

[`num1`](#num1), ..., `numN`

:   An integer between `0` and `0x10FFFF` (inclusive) representing a
    Unicode code point.



 
### Return value 

 
A string created by using the specified sequence of code points.



 
### Exceptions

 

[`RangeError`](../rangeerror)

:   Thrown if `numN` is not an integer, is less than `0`, or is greater
    than `0x10FFFF` after being converted to a number.



 
Description
-----------

 
Because `fromCodePoint()` is a static method of `String`, you always use
it as `String.fromCodePoint()`, rather than as a method of a `String`
value you created.

Unicode code points range from `0` to `1114111` (`0x10FFFF`). In UTF-16,
each string index is a code unit with value `0` -- `65535`. Higher code
points are represented by *a pair* of 16-bit surrogate
pseudo-characters. Therefore, `fromCodePoint()` may return a string
whose [`length`](length) (in UTF-16 code units) is larger than the
number of arguments passed. For information on Unicode, see [UTF-16
characters, Unicode code points, and grapheme
clusters](../string#utf-16_characters_unicode_code_points_and_grapheme_clusters).



 
Examples
--------


 
### Using fromCodePoint() 

 
Valid input:

 
 
[js]


```js
String.fromCodePoint(42); // "*"
String.fromCodePoint(65, 90); // "AZ"
String.fromCodePoint(0x404); // "\u0404" === "Є"
String.fromCodePoint(0x2f804); // "\uD87E\uDC04"
String.fromCodePoint(194564); // "\uD87E\uDC04"
String.fromCodePoint(0x1d306, 0x61, 0x1d307); // "\uD834\uDF06a\uD834\uDF07"
```


Invalid input:

 
 
[js]


```js
String.fromCodePoint("_"); // RangeError
String.fromCodePoint(Infinity); // RangeError
String.fromCodePoint(-1); // RangeError
String.fromCodePoint(3.14); // RangeError
String.fromCodePoint(3e-2); // RangeError
String.fromCodePoint(NaN); // RangeError
```




 
### Compared to fromCharCode() 

 
[`String.fromCharCode()`](fromcharcode) cannot return supplementary
characters (i.e. code points `0x010000` -- `0x10FFFF`) by specifying
their code point. Instead, it requires the UTF-16 surrogate pair in
order to return a supplementary character:

 
 
[js]


```js
String.fromCharCode(0xd83c, 0xdf03); // Code Point U+1F303 "Night with
String.fromCharCode(55356, 57091); // Stars" === "\uD83C\uDF03"
```


`String.fromCodePoint()`, on the other hand, can return 4-byte
supplementary characters, as well as the more common 2-byte BMP
characters, by specifying their code point (which is equivalent to the
UTF-32 code unit):

 
 
[js]


```js
String.fromCodePoint(0x1f303); // or 127747 in decimal
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-string.fromcodepoint]](https://tc39.es/ecma262/multipage/text-processing.html#sec-string.fromcodepoint)

  ---------------------------------------------------------------------------------------------------------------------


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

`fromCodePoint`

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

 
-   [Polyfill of `String.fromCodePoint` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-string-and-regexp)
-   [`String.fromCharCode()`](fromcharcode)
-   [`String.prototype.charAt()`](charat)
-   [`String.prototype.codePointAt()`](codepointat)
-   [`String.prototype.charCodeAt()`](charcodeat)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/fromCodePoint>

