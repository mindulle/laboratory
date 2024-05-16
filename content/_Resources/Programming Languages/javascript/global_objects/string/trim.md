String.prototype.trim()
=======================

 
The `trim()` method of [`String`](../string) values removes whitespace
from both ends of this string and returns a new string, without
modifying the original string.

To return a new string with whitespace trimmed from just one end, use
[`trimStart()`](trimstart) or [`trimEnd()`](trimend).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
trim()
```




 
### Parameters

 
None.



 
### Return value 

 
A new string representing `str` stripped of whitespace from both its
beginning and end. Whitespace is defined as [white
space](../../lexical_grammar#white_space) characters plus [line
terminators](../../lexical_grammar#line_terminators).

If neither the beginning or end of `str` has any whitespace, a new
string is still returned (essentially a copy of `str`).



 
Examples
--------


 
### Using trim() 

 
The following example trims whitespace from both ends of `str`.

 
 
[js]


```js
const str = "   foo  ";
console.log(str.trim()); // 'foo'
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-string.prototype.trim]](https://tc39.es/ecma262/multipage/text-processing.html#sec-string.prototype.trim)

  -----------------------------------------------------------------------------------------------------------------------


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

`trim`

4

12

3.5

10.5

5

18

4

11

5

1.0

≤37

1.0

0.10.0

 
See also 
--------

 
-   [`String.prototype.trimStart()`](trimstart)
-   [`String.prototype.trimEnd()`](trimend)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/trim>

