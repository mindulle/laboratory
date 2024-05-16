SyntaxError
===========

 
The `SyntaxError` object represents an error when trying to interpret
syntactically invalid code. It is thrown when the JavaScript engine
encounters tokens or token order that does not conform to the syntax of
the language when parsing code.

`SyntaxError` is a [serializable
object](https://developer.mozilla.org/en-US/docs/Glossary/Serializable_object),
so it can be cloned with
[`structuredClone()`](https://developer.mozilla.org/en-US/docs/Web/API/structuredClone)
or copied between
[Workers](https://developer.mozilla.org/en-US/docs/Web/API/Worker) using
[`postMessage()`](https://developer.mozilla.org/en-US/docs/Web/API/Worker/postMessage).

`SyntaxError` is a subclass of [`Error`](error).


 
Constructor
-----------

 

[`SyntaxError()`](syntaxerror/syntaxerror)

:   Creates a new `SyntaxError` object.



 
Instance properties 
-------------------

 
*Also inherits instance properties from its parent [`Error`](error)*.

These properties are defined on `SyntaxError.prototype` and shared by
all `SyntaxError` instances.

[`SyntaxError.prototype.constructor`](object/constructor)

:   The constructor function that created the instance object. For
    `SyntaxError` instances, the initial value is the
    [`SyntaxError`](syntaxerror/syntaxerror) constructor.

[`SyntaxError.prototype.name`](error/name)

:   Represents the name for the type of error. For
    `SyntaxError.prototype.name`, the initial value is `"SyntaxError"`.



 
Instance methods 
----------------

 
*Inherits instance methods from its parent [`Error`](error)*.



 
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

 
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-native-error-types-used-in-this-standard-syntaxerror]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-native-error-types-used-in-this-standard-syntaxerror)

  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


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

`serializable_object`

77

79

103\[\"Version 103 serializable properties: `name`, `message`, `cause`,
`fileName`, `lineNumber` and `columnNumber`.\", \"Version 104 also
serializes `stack` in the main thread
([`window.postMessage()`](https://developer.mozilla.org/docs/Web/API/Window/postMessage)
and
[`structuredClone()`](https://developer.mozilla.org/docs/Web/API/structuredClone)).\",
\"Version 110 also serializes `stack` in workers
([`worker.postMessage()`](https://developer.mozilla.org/docs/Web/API/Worker/postMessage)
and
[`structuredClone()`](https://developer.mozilla.org/docs/Web/API/structuredClone)).\"\]

64

No

77

103\[\"Version 103 serializable properties: `name`, `message`, `cause`,
`fileName`, `lineNumber` and `columnNumber`.\", \"Version 104 also
serializes `stack` in the main thread
([`window.postMessage()`](https://developer.mozilla.org/docs/Web/API/Window/postMessage)
and
[`structuredClone()`](https://developer.mozilla.org/docs/Web/API/structuredClone)).\",
\"Version 110 also serializes `stack` in workers
([`worker.postMessage()`](https://developer.mozilla.org/docs/Web/API/Worker/postMessage)
and
[`structuredClone()`](https://developer.mozilla.org/docs/Web/API/structuredClone)).\"\]

55

No

12.0

77

No

No

 
See also 
--------

 
-   [`Error`](error)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/SyntaxError>

