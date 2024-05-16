String.prototype.at()
=====================

 
The `at()` method of [`String`](../string) values takes an integer value
and returns a new [`String`](../string) consisting of the single UTF-16
code unit located at the specified offset. This method allows for
positive and negative integers. Negative integers count back from the
last string character.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
at(index)
```




 
### Parameters

 

[`index`](#index)

:   The index (position) of the string character to be returned.
    Supports relative indexing from the end of the string when passed a
    negative index; i.e. if a negative number is used, the character
    returned will be found by counting back from the end of the string.



 
### Return value 

 
A [`String`](../string) consisting of the single UTF-16 code unit
located at the specified position. Returns [`undefined`](../undefined)
if the given index can not be found.



 
Examples
--------


 
### Return the last character of a string 

 
The following example provides a function which returns the last
character found in a specified string.

 
 
[js]


```js
// A function which returns the last character of a given string
function returnLast(arr) {
  return arr.at(-1);
}

let invoiceRef = "myinvoice01";

console.log(returnLast(invoiceRef)); // '1'

invoiceRef = "myinvoice02";

console.log(returnLast(invoiceRef)); // '2'
```




 
### Comparing methods 

 
Here we compare different ways to select the penultimate (last but one)
character of a [`String`](../string). Whilst all below methods are
valid, it highlights the succinctness and readability of the `at()`
method.

 
 
[js]


```js
const myString = "Every green bus drives fast.";

// Using length property and charAt() method
const lengthWay = myString.charAt(myString.length - 2);
console.log(lengthWay); // 't'

// Using slice() method
const sliceWay = myString.slice(-2, -1);
console.log(sliceWay); // 't'

// Using at() method
const atWay = myString.at(-2);
console.log(atWay); // 't'
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-string.prototype.at]](https://tc39.es/ecma262/multipage/text-processing.html#sec-string.prototype.at)

  -------------------------------------------------------------------------------------------------------------------


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

`at`

92

92

90

78

15.4

92

90

65

15.4

16.0

92

1.12

16.6.0

 
See also 
--------

 
-   [Polyfill of `String.prototype.at` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-string-and-regexp)
-   [`String.prototype.indexOf()`](indexof)
-   [`String.prototype.lastIndexOf()`](lastindexof)
-   [`String.prototype.charCodeAt()`](charcodeat)
-   [`String.prototype.codePointAt()`](codepointat)
-   [`String.prototype.split()`](split)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/at>

