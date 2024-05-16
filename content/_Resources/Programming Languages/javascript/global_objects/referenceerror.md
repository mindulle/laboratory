ReferenceError
==============

 
The `ReferenceError` object represents an error when a variable that
doesn\'t exist (or hasn\'t yet been initialized) in the current scope is
referenced.

`ReferenceError` is a [serializable
object](https://developer.mozilla.org/en-US/docs/Glossary/Serializable_object),
so it can be cloned with
[`structuredClone()`](https://developer.mozilla.org/en-US/docs/Web/API/structuredClone)
or copied between
[Workers](https://developer.mozilla.org/en-US/docs/Web/API/Worker) using
[`postMessage()`](https://developer.mozilla.org/en-US/docs/Web/API/Worker/postMessage).

`ReferenceError` is a subclass of [`Error`](error).


 
Constructor
-----------

 

[`ReferenceError()`](referenceerror/referenceerror)

:   Creates a new `ReferenceError` object.



 
Instance properties 
-------------------

 
*Also inherits instance properties from its parent [`Error`](error)*.

These properties are defined on `ReferenceError.prototype` and shared by
all `ReferenceError` instances.

[`ReferenceError.prototype.constructor`](object/constructor)

:   The constructor function that created the instance object. For
    `ReferenceError` instances, the initial value is the
    [`ReferenceError`](referenceerror/referenceerror) constructor.

[`ReferenceError.prototype.name`](error/name)

:   Represents the name for the type of error. For
    `ReferenceError.prototype.name`, the initial value is
    `"ReferenceError"`.



 
Instance methods 
----------------

 
*Inherits instance methods from its parent [`Error`](error)*.



 
Examples
--------


 
### Catching a ReferenceError 

 
 
 
[js]


```js
try {
  let a = undefinedVariable;
} catch (e) {
  console.log(e instanceof ReferenceError); // true
  console.log(e.message); // "undefinedVariable is not defined"
  console.log(e.name); // "ReferenceError"
  console.log(e.stack); // Stack of the error
}
```




 
### Creating a ReferenceError 

 
 
 
[js]


```js
try {
  throw new ReferenceError("Hello");
} catch (e) {
  console.log(e instanceof ReferenceError); // true
  console.log(e.message); // "Hello"
  console.log(e.name); // "ReferenceError"
  console.log(e.stack); // Stack of the error
}
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-native-error-types-used-in-this-standard-referenceerror]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-native-error-types-used-in-this-standard-referenceerror)

  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


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

`ReferenceError`

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

`ReferenceError`

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
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ReferenceError>

