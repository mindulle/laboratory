Error: message
==============

 
The `message` data property of an [`Error`](../error) instance is a
human-readable description of the error.


 
Value
-----

 
A string corresponding to the value passed to the [`Error()`](error)
constructor as the first argument.

 
Property attributes of `Error: message`




Writable

yes

Enumerable

no

Configurable

yes

 
Description
-----------

 
This property contains a brief description of the error if one is
available or has been set. The `message` property combined with the
[`name`](name) property is used by the
[`Error.prototype.toString()`](tostring) method to create a string
representation of the Error.

By default, the `message` property is an empty string, but this behavior
can be overridden for an instance by specifying a message as the first
argument to the [`Error`](error) constructor.



 
Examples
--------


 
### Throwing a custom error 

 
 
 
[js]


```js
const e = new Error("Could not parse input");
// e.message is 'Could not parse input'
throw e;
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-error.prototype.message]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-error.prototype.message)

  -------------------------------------------------------------------------------------------------------------------------------


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

`message`

1

12

1

5

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

 
-   [`Error.prototype.name`](name)
-   [`Error.prototype.toString()`](tostring)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error/message>

