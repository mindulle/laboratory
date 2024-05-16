String.prototype.trimStart()
============================

 
The `trimStart()` method of [`String`](../string) values removes
whitespace from the beginning of this string and returns a new string,
without modifying the original string. `trimLeft()` is an alias of this
method.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
trimStart()

trimLeft()
```




 
### Parameters

 
None.



 
### Return value 

 
A new string representing `str` stripped of whitespace from its
beginning (left side). Whitespace is defined as [white
space](../../lexical_grammar#white_space) characters plus [line
terminators](../../lexical_grammar#line_terminators).

If the beginning of `str` has no whitespace, a new string is still
returned (essentially a copy of `str`).



 
### Aliasing

 
After [`trim()`](trim) was standardized, engines also implemented the
non-standard method `trimLeft`. However, for consistency with
[`padStart()`](padstart), when the method got standardized, its name was
chosen as `trimStart`. For web compatibility reasons, `trimLeft` remains
as an alias to `trimStart`, and they refer to the exact same function
object. In some engines this means:

 
 
[js]


```js
String.prototype.trimLeft.name === "trimStart";
```




 
Examples
--------


 
### Using trimStart() 

 
The following example trims whitespace from the start of `str`, but not
from its end.

 
 
[js]


```js
let str = "   foo  ";

console.log(str.length); // 8

str = str.trimStart();
console.log(str.length); // 5
console.log(str); // 'foo  '
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-string.prototype.trimstart]](https://tc39.es/ecma262/multipage/text-processing.html#sec-string.prototype.trimstart)

  ---------------------------------------------------------------------------------------------------------------------------------


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

`trimStart`

664

7912

613.5

5315

12

6618

614

4714

12

9.01.0

66≤37

1.01.0

10.0.00.12.0

 
See also 
--------

 
-   [Polyfill of `String.prototype.trimStart` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-string-and-regexp)
-   [`String.prototype.trim()`](trim)
-   [`String.prototype.trimEnd()`](trimend)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/trimStart>

