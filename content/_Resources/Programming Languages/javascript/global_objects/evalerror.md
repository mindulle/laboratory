EvalError
=========

 
The `EvalError` object indicates an error regarding the global
[`eval()`](eval) function. This exception is not thrown by JavaScript
anymore, however the `EvalError` object remains for compatibility.

`EvalError` is a [serializable
object](https://developer.mozilla.org/en-US/docs/Glossary/Serializable_object),
so it can be cloned with
[`structuredClone()`](https://developer.mozilla.org/en-US/docs/Web/API/structuredClone)
or copied between
[Workers](https://developer.mozilla.org/en-US/docs/Web/API/Worker) using
[`postMessage()`](https://developer.mozilla.org/en-US/docs/Web/API/Worker/postMessage).

`EvalError` is a subclass of [`Error`](error).


 
Constructor
-----------

 

[`EvalError()`](evalerror/evalerror)

:   Creates a new `EvalError` object.



 
Instance properties 
-------------------

 
*Also inherits instance properties from its parent [`Error`](error)*.

These properties are defined on `EvalError.prototype` and shared by all
`EvalError` instances.

[`EvalError.prototype.constructor`](object/constructor)

:   The constructor function that created the instance object. For
    `EvalError` instances, the initial value is the
    [`EvalError`](evalerror/evalerror) constructor.

[`EvalError.prototype.name`](error/name)

:   Represents the name for the type of error. For
    `EvalError.prototype.name`, the initial value is `"EvalError"`.



 
Instance methods 
----------------

 
*Inherits instance methods from its parent [`Error`](error)*.



 
Examples
--------


 
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

 
  -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-native-error-types-used-in-this-standard-evalerror]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-native-error-types-used-in-this-standard-evalerror)

  -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


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
-   [`eval()`](eval)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/EvalError>

