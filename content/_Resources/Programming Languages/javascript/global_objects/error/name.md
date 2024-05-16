Error.prototype.name
====================

 
The `name` data property of `Error.prototype` is shared by all
[`Error`](../error) instances. It represents the name for the type of
error. For `Error.prototype.name`, the initial value is `"Error"`.
Subclasses like [`TypeError`](../typeerror) and
[`SyntaxError`](../syntaxerror) provide their own `name` properties.


 
Value
-----

 
A string. For `Error.prototype.name`, the initial value is `"Error"`.

 
Property attributes of `Error.prototype.name`




Writable

yes

Enumerable

no

Configurable

yes

 
Description
-----------

 
By default, [`Error`](../error) instances are given the name \"Error\".
The `name` property, in addition to the [`message`](message) property,
is used by the [`Error.prototype.toString()`](tostring) method to create
a string representation of the error.



 
Examples
--------


 
### Throwing a custom error 

 
 
 
[js]


```js
const e = new Error("Malformed input"); // e.name is 'Error'

e.name = "ParseError";
throw e;
// e.toString() would return 'ParseError: Malformed input'
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-error.prototype.name]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-error.prototype.name)

  -------------------------------------------------------------------------------------------------------------------------


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

`name`

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

 
-   [`Error.prototype.message`](message)
-   [`Error.prototype.toString()`](tostring)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error/name>

