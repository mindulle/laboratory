SyntaxError() constructor
=========================

 
The `SyntaxError()` constructor creates [`SyntaxError`](../syntaxerror)
objects.


 
Syntax
------

 
 
 
[js]


```js
new SyntaxError()
new SyntaxError(message)
new SyntaxError(message, options)
new SyntaxError(message, fileName)
new SyntaxError(message, fileName, lineNumber)

SyntaxError()
SyntaxError(message)
SyntaxError(message, options)
SyntaxError(message, fileName)
SyntaxError(message, fileName, lineNumber)
```


 
**Note:** `SyntaxError()` can be called with or without
[`new`](../../operators/new). Both create a new `SyntaxError` instance.




 
### Parameters

 

[`message`](#message) [Optional]

:   Human-readable description of the error

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


 
### Catching a SyntaxError 

 
 
 
[js]


```js
try {
  eval("hoo bar");
} catch (e) {
  console.log(e instanceof SyntaxError); // true
  console.log(e.message);
  console.log(e.name); // "SyntaxError"
  console.log(e.stack); // Stack of the error
}
```




 
### Creating a SyntaxError 

 
 
 
[js]


```js
try {
  throw new SyntaxError("Hello");
} catch (e) {
  console.log(e instanceof SyntaxError); // true
  console.log(e.message); // "Hello"
  console.log(e.name); // "SyntaxError"
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

`SyntaxError`

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



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/SyntaxError/SyntaxError>

