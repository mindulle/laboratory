String.prototype.trimEnd()
==========================

 
The `trimEnd()` method of [`String`](../string) values removes
whitespace from the end of this string and returns a new string, without
modifying the original string. `trimRight()` is an alias of this method.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
trimEnd()

trimRight()
```




 
### Parameters

 
None.



 
### Return value 

 
A new string representing `str` stripped of whitespace from its end
(right side). Whitespace is defined as [white
space](../../lexical_grammar#white_space) characters plus [line
terminators](../../lexical_grammar#line_terminators).

If the end of `str` has no whitespace, a new string is still returned
(essentially a copy of `str`).



 
### Aliasing

 
After [`trim()`](trim) was standardized, engines also implemented the
non-standard method `trimRight`. However, for consistency with
[`padEnd()`](padend), when the method got standardized, its name was
chosen as `trimEnd`. For web compatibility reasons, `trimRight` remains
as an alias to `trimEnd`, and they refer to the exact same function
object. In some engines this means:

 
 
[js]


```js
String.prototype.trimRight.name === "trimEnd";
```




 
Examples
--------


 
### Using trimEnd() 

 
The following example trims whitespace from the end of `str`, but not
from its start.

 
 
[js]


```js
let str = "   foo  ";

console.log(str.length); // 8

str = str.trimEnd();
console.log(str.length); // 6
console.log(str); // '   foo'
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-string.prototype.trimend]](https://tc39.es/ecma262/multipage/text-processing.html#sec-string.prototype.trimend)

  -----------------------------------------------------------------------------------------------------------------------------


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

`trimEnd`

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

 
-   [Polyfill of `String.prototype.trimEnd` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-string-and-regexp)
-   [`String.prototype.trim()`](trim)
-   [`String.prototype.trimStart()`](trimstart)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/trimEnd>

