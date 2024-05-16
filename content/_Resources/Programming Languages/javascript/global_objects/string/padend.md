String.prototype.padEnd()
=========================

 
The `padEnd()` method of [`String`](../string) values pads this string
with a given string (repeated, if needed) so that the resulting string
reaches a given length. The padding is applied from the end of this
string.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
padEnd(targetLength)
padEnd(targetLength, padString)
```




 
### Parameters

 

[`targetLength`](#targetlength)

:   The length of the resulting string once the current `str` has been
    padded. If the value is less than or equal to `str.length`, the
    current string will be returned as-is.

[`padString`](#padstring) [Optional]

:   The string to pad the current `str` with. If `padString` is too long
    to stay within `targetLength`, it will be truncated: for
    left-to-right languages the left-most part and for right-to-left
    languages the right-most will be applied. The default value for this
    parameter is \" \" (`U+0020`).



 
### Return value 

 
A [`String`](../string) of the specified `targetLength` with the
`padString` applied at the end of the current `str`.



 
Examples
--------


 
### Using padEnd 

 
 
 
[js]


```js
"abc".padEnd(10); // "abc       "
"abc".padEnd(10, "foo"); // "abcfoofoof"
"abc".padEnd(6, "123456"); // "abc123"
"abc".padEnd(1); // "abc"
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-string.prototype.padend]](https://tc39.es/ecma262/multipage/text-processing.html#sec-string.prototype.padend)

  ---------------------------------------------------------------------------------------------------------------------------


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

`padEnd`

57

15

48

44

10

57

48

43

10

7.0

57

1.0

8.0.0

 
See also 
--------

 
-   [Polyfill of `String.prototype.padEnd` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-string-and-regexp)
-   [`String.prototype.padStart()`](padstart)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/padEnd>

