EvalError() constructor
=======================

 
The `EvalError()` constructor creates [`EvalError`](../evalerror)
objects.


 
Syntax
------

 
 
 
[js]


```js
new EvalError()
new EvalError(message)
new EvalError(message, options)
new EvalError(message, fileName)
new EvalError(message, fileName, lineNumber)

EvalError()
EvalError(message)
EvalError(message, options)
EvalError(message, fileName)
EvalError(message, fileName, lineNumber)
```


 
**Note:** `EvalError()` can be called with or without
[`new`](../../operators/new). Both create a new `EvalError` instance.




 
### Parameters

 

[`message`](#message) [Optional]

:   Human-readable description of the error.

[`options`](#options) [Optional]

:   An object that has the following properties:

    [`cause`](#cause) [Optional]

    :   A property indicating the specific cause of the error. When
        catching and re-throwing an error with a more-specific or useful
        error message, this property can be used to pass the original
        error.

[`fileName`](#filename) [Optional]

:   The name of the file containing the code that caused the exception

[`lineNumber`](#linenumber) [Optional]

:   The line number of the code that caused the exception



 
Examples
--------

 
`EvalError` is not used in the current ECMAScript specification and will
thus not be thrown by the runtime. However, the object itself remains
for backwards compatibility with earlier versions of the specification.



 
### Creating an EvalError 

 
 
 
[js]


```js
try {
  throw new EvalError("Hello");
} catch (e) {
  console.log(e instanceof EvalError); // true
  console.log(e.message); // "Hello"
  console.log(e.name); // "EvalError"
  console.log(e.stack); // Stack of the error
}
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-nativeerror-constructors]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-nativeerror-constructors)

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

`EvalError`

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

 
-   [`Error`](../error)
-   [`eval()`](../eval)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/EvalError/EvalError>

