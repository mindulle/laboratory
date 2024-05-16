String.prototype.valueOf()
==========================

 
The `valueOf()` method of [`String`](../string) values returns this
string value.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
valueOf()
```




 
### Parameters

 
None.



 
### Return value 

 
A string representing the primitive value of a given
[`String`](../string) object.



 
Description
-----------

 
The `valueOf()` method of [`String`](../string) returns the primitive
value of a [`String`](../string) object as a string data type. This
value is equivalent to [`String.prototype.toString()`](tostring).

This method is usually called internally by JavaScript and not
explicitly in code.



 
Examples
--------


 
### Using `valueOf()` 

 
 
 
[js]


```js
const x = new String("Hello world");
console.log(x.valueOf()); // 'Hello world'
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-string.prototype.valueof]](https://tc39.es/ecma262/multipage/text-processing.html#sec-string.prototype.valueof)

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

`valueOf`

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

 
-   [`String.prototype.toString()`](tostring)
-   [`Object.prototype.valueOf()`](../object/valueof)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/valueOf>

