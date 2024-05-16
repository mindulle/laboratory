RangeError: argument is not a valid code point
==============================================

 
The JavaScript exception \"Invalid code point\" occurs when
[`NaN`](../global_objects/nan) values, negative Integers (-1),
non-Integers (5.4), or values larger than 0x10FFFF (1114111) are used
with [`String.fromCodePoint()`](../global_objects/string/fromcodepoint).


 
Message
-------

 
```text
RangeError: Invalid code point -1 (V8-based)
RangeError: -1 is not a valid code point (Firefox)
RangeError: Arguments contain a value that is out of range of code points (Safari)
```



 
Error type 
----------

 
[`RangeError`](../global_objects/rangeerror)



 
What went wrong? 
----------------

 
[`String.fromCodePoint()`](../global_objects/string/fromcodepoint)
throws this error when passed [`NaN`](../global_objects/nan) values,
negative Integers (-1), non-Integers (5.4), or values larger than
0x10FFFF (1114111).

A [code point](https://en.wikipedia.org/wiki/Code_point) is a value in
the Unicode codespace; that is, the range of integers from `0` to
`0x10FFFF`.



 
Examples
--------


 
### Invalid cases 

 
 
 
[js]


```js
String.fromCodePoint("_"); // RangeError
String.fromCodePoint(Infinity); // RangeError
String.fromCodePoint(-1); // RangeError
String.fromCodePoint(3.14); // RangeError
String.fromCodePoint(3e-2); // RangeError
String.fromCodePoint(NaN); // RangeError
```




 
### Valid cases 

 
 
 
[js]


```js
String.fromCodePoint(42); // "*"
String.fromCodePoint(65, 90); // "AZ"
String.fromCodePoint(0x404); // 'Є' (U+0404)
String.fromCodePoint(0x2f804); // '你' (U+2F804)
String.fromCodePoint(194564); // '你'
String.fromCodePoint(0x1d306, 0x61, 0x1d307); // '𝌆a𝌇'
```




 
See also 
--------

 
-   [`String.fromCodePoint()`](../global_objects/string/fromcodepoint)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Not_a_valid_code_point>

