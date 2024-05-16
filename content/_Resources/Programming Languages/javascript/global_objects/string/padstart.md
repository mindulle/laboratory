String.prototype.padStart()
===========================

 
The `padStart()` method of [`String`](../string) values pads this string
with another string (multiple times, if needed) until the resulting
string reaches the given length. The padding is applied from the start
of this string.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
padStart(targetLength)
padStart(targetLength, padString)
```




 
### Parameters

 

[`targetLength`](#targetlength)

:   The length of the resulting string once the current `str` has been
    padded. If the value is less than or equal to `str.length`, then
    `str` is returned as-is.

[`padString`](#padstring) [Optional]

:   The string to pad the current `str` with. If `padString` is too long
    to stay within the `targetLength`, it will be truncated from the
    end. The default value is the unicode \"space\" character (U+0020).



 
### Return value 

 
A [`String`](../string) of the specified `targetLength` with `padString`
applied from the start.



 
Examples
--------


 
### Basic examples 

 
 
 
[js]


```js
"abc".padStart(10); // "       abc"
"abc".padStart(10, "foo"); // "foofoofabc"
"abc".padStart(6, "123465"); // "123abc"
"abc".padStart(8, "0"); // "00000abc"
"abc".padStart(1); // "abc"
```




 
### Fixed width string number conversion 

 
 
 
[js]


```js
// JavaScript version of: (unsigned)
// printf "%0*d" width num
function leftFillNum(num, targetLength) {
  return num.toString().padStart(targetLength, "0");
}

const num = 123;
console.log(leftFillNum(num, 5)); // "00123"
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-string.prototype.padstart]](https://tc39.es/ecma262/multipage/text-processing.html#sec-string.prototype.padstart)

  -------------------------------------------------------------------------------------------------------------------------------


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

`padStart`

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

 
-   [Polyfill of `String.prototype.padStart` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-string-and-regexp)
-   [`String.prototype.padEnd()`](padend)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/padStart>

