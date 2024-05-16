String.prototype.toUpperCase()
==============================

 
The `toUpperCase()` method of [`String`](../string) values returns this
string converted to uppercase.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
toUpperCase()
```




 
### Parameters

 
None.



 
### Return value 

 
A new string representing the calling string converted to upper case.



 
Description
-----------

 
The `toUpperCase()` method returns the value of the string converted to
uppercase. This method does not affect the value of the string itself
since JavaScript strings are immutable.



 
Examples
--------


 
### Basic usage 

 
 
 
[js]


```js
console.log("alphabet".toUpperCase()); // 'ALPHABET'
```




 
### Conversion of non-string `this` values to strings 

 
This method will convert any non-string value to a string, when you set
its `this` to a value that is not a string:

 
 
[js]


```js
const a = String.prototype.toUpperCase.call({
  toString() {
    return "abcdef";
  },
});

const b = String.prototype.toUpperCase.call(true);

// prints out 'ABCDEF TRUE'.
console.log(a, b);
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-string.prototype.touppercase]](https://tc39.es/ecma262/multipage/text-processing.html#sec-string.prototype.touppercase)

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

`toUpperCase`

1

12

1

3

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

 
-   [`String.prototype.toLocaleLowerCase()`](tolocalelowercase)
-   [`String.prototype.toLocaleUpperCase()`](tolocaleuppercase)
-   [`String.prototype.toLowerCase()`](tolowercase)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/toUpperCase>

