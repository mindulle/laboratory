String.prototype.repeat()
=========================

 
The `repeat()` method of [`String`](../string) values constructs and
returns a new string which contains the specified number of copies of
this string, concatenated together.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
repeat(count)
```




 
### Parameters

 

[`count`](#count)

:   An integer between `0` and
    [`+Infinity`](../number/positive_infinity), indicating the number of
    times to repeat the string.



 
### Return value 

 
A new string containing the specified number of copies of the given
string.



 
### Exceptions

 

[`RangeError`](../rangeerror)

:   Thrown if `count` is negative or if `count` overflows maximum string
    length.



 
Examples
--------


 
### Using repeat() 

 
 
 
[js]


```js
"abc".repeat(-1); // RangeError
"abc".repeat(0); // ''
"abc".repeat(1); // 'abc'
"abc".repeat(2); // 'abcabc'
"abc".repeat(3.5); // 'abcabcabc' (count will be converted to integer)
"abc".repeat(1 / 0); // RangeError

({ toString: () => "abc", repeat: String.prototype.repeat }).repeat(2);
// 'abcabc' (repeat() is a generic method)
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-string.prototype.repeat]](https://tc39.es/ecma262/multipage/text-processing.html#sec-string.prototype.repeat)

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

`repeat`

41

12

24

28

9

36

24

28

9

3.0

41

1.0

4.0.0

 
See also 
--------

 
-   [Polyfill of `String.prototype.repeat` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-string-and-regexp)
-   [`String.prototype.concat()`](concat)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/repeat>

