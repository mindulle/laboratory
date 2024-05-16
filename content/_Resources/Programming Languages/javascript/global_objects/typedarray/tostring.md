TypedArray.prototype.toString()
===============================

 
The `toString()` method of [`TypedArray`](../typedarray) instances
returns a string representing the specified typed array and its
elements. This method has the same algorithm as
[`Array.prototype.toString()`](../array/tostring).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
toString()
```




 
### Parameters

 
None.



 
### Return value 

 
A string representing the elements of the typed array.



 
Description
-----------

 
See [`Array.prototype.toString()`](../array/tostring) for more details.
This method is not generic and can only be called on typed array
instances.



 
Examples
--------


 
### Converting a typed array to a string 

 
 
 
[js]


```js
const uint8 = new Uint8Array([1, 2, 3]);
// Explicit conversion
console.log(uint8.toString()); // 1,2,3
// Implicit conversion
console.log(`${uint8}`); // 1,2,3
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\# sec-%typedarray%.prototype.tostring]](#)

  -----------------------------------------------------------------------


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

`toString`

7

12

51

11.6

5.1

18

51

12

5

1.0

≤37

1.0

0.10.0

 
See also 
--------

 
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [`TypedArray`](../typedarray)
-   [`TypedArray.prototype.join()`](join)
-   [`TypedArray.prototype.toLocaleString()`](tolocalestring)
-   [`Array.prototype.toString()`](../array/tostring)
-   [`String.prototype.toString()`](../string/tostring)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/toString>

