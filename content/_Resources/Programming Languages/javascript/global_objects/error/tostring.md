Error.prototype.toString()
==========================

 
The `toString()` method of [`Error`](../error) instances returns a
string representing this error.


 
Syntax
------

 
 
 
[js]


```js
toString()
```




 
### Parameters

 
None.



 
### Return value 

 
A string representing the specified [`Error`](../error) object.



 
Description
-----------

 
The [`Error`](../error) object overrides the
[`Object.prototype.toString()`](../object/tostring) method inherited by
all objects. Its semantics are as follows:

 
 
[js]


```js
Error.prototype.toString = function () {
  if (
    this === null ||
    (typeof this !== "object" && typeof this !== "function")
  ) {
    throw new TypeError();
  }
  let name = this.name;
  name = name === undefined ? "Error" : `${name}`;
  let msg = this.message;
  msg = msg === undefined ? "" : `${msg}`;
  if (name === "") {
    return msg;
  }
  if (msg === "") {
    return name;
  }
  return `${name}: ${msg}`;
};
```




 
Examples
--------


 
### Using toString() 

 
 
 
[js]


```js
const e1 = new Error("fatal error");
console.log(e1.toString()); // "Error: fatal error"

const e2 = new Error("fatal error");
e2.name = undefined;
console.log(e2.toString()); // "Error: fatal error"

const e3 = new Error("fatal error");
e3.name = "";
console.log(e3.toString()); // "fatal error"

const e4 = new Error("fatal error");
e4.name = "";
e4.message = undefined;
console.log(e4.toString()); // ""

const e5 = new Error("fatal error");
e5.name = "hello";
e5.message = undefined;
console.log(e5.toString()); // "hello"
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-error.prototype.tostring]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-error.prototype.tostring)

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

`toString`

1

12

1

4

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

 
-   [Polyfill of `Error.prototype.toString` with many bug fixes in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-error)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error/toString>

