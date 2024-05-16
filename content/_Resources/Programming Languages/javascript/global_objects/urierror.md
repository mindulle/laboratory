URIError
========

 
The `URIError` object represents an error when a global URI handling
function was used in a wrong way.

`URIError` is a [serializable
object](https://developer.mozilla.org/en-US/docs/Glossary/Serializable_object),
so it can be cloned with
[`structuredClone()`](https://developer.mozilla.org/en-US/docs/Web/API/structuredClone)
or copied between
[Workers](https://developer.mozilla.org/en-US/docs/Web/API/Worker) using
[`postMessage()`](https://developer.mozilla.org/en-US/docs/Web/API/Worker/postMessage).

`URIError` is a subclass of [`Error`](error).


 
Constructor
-----------

 

[`URIError()`](urierror/urierror)

:   Creates a new `URIError` object.



 
Instance properties 
-------------------

 
*Also inherits instance properties from its parent [`Error`](error)*.

These properties are defined on `URIError.prototype` and shared by all
`URIError` instances.

[`URIError.prototype.constructor`](object/constructor)

:   The constructor function that created the instance object. For
    `URIError` instances, the initial value is the
    [`URIError`](urierror/urierror) constructor.

[`URIError.prototype.name`](error/name)

:   Represents the name for the type of error. For
    `URIError.prototype.name`, the initial value is `"URIError"`.



 
Instance methods 
----------------

 
*Inherits instance methods from its parent [`Error`](error)*.



 
Examples
--------


 
### Catching an URIError 

 
 
 
[js]


```js
try {
  decodeURIComponent("%");
} catch (e) {
  console.log(e instanceof URIError); // true
  console.log(e.message); // "malformed URI sequence"
  console.log(e.name); // "URIError"
  console.log(e.stack); // Stack of the error
}
```




 
### Creating an URIError 

 
 
 
[js]


```js
try {
  throw new URIError("Hello");
} catch (e) {
  console.log(e instanceof URIError); // true
  console.log(e.message); // "Hello"
  console.log(e.name); // "URIError"
  console.log(e.stack); // Stack of the error
}
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-native-error-types-used-in-this-standard-urierror]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-native-error-types-used-in-this-standard-urierror)

  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


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

`URIError`

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

`URIError`

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
-   [`decodeURI()`](decodeuri)
-   [`decodeURIComponent()`](decodeuricomponent)
-   [`encodeURI()`](encodeuri)
-   [`encodeURIComponent()`](encodeuricomponent)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/URIError>

