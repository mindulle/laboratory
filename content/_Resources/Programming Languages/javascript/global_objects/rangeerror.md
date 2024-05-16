RangeError
==========

 
The `RangeError` object indicates an error when a value is not in the
set or range of allowed values.


 
Description
-----------

 
A `RangeError` is thrown when trying to pass a value as an argument to a
function that does not allow a range that includes the value.

This can be encountered when:

-   passing a value that is not one of the allowed string values to
    [`String.prototype.normalize()`](string/normalize), or
-   when attempting to create an array of an illegal length with the
    [`Array`](array) constructor, or
-   when passing bad values to the numeric methods
    [`Number.prototype.toExponential()`](number/toexponential),
    [`Number.prototype.toFixed()`](number/tofixed) or
    [`Number.prototype.toPrecision()`](number/toprecision).

`RangeError` is a [serializable
object](https://developer.mozilla.org/en-US/docs/Glossary/Serializable_object),
so it can be cloned with
[`structuredClone()`](https://developer.mozilla.org/en-US/docs/Web/API/structuredClone)
or copied between
[Workers](https://developer.mozilla.org/en-US/docs/Web/API/Worker) using
[`postMessage()`](https://developer.mozilla.org/en-US/docs/Web/API/Worker/postMessage).

`RangeError` is a subclass of [`Error`](error).



 
Constructor
-----------

 

[`RangeError()`](rangeerror/rangeerror)

:   Creates a new `RangeError` object.



 
Instance properties 
-------------------

 
*Also inherits instance properties from its parent [`Error`](error)*.

These properties are defined on `RangeError.prototype` and shared by all
`RangeError` instances.

[`RangeError.prototype.constructor`](object/constructor)

:   The constructor function that created the instance object. For
    `RangeError` instances, the initial value is the
    [`RangeError`](rangeerror/rangeerror) constructor.

[`RangeError.prototype.name`](error/name)

:   Represents the name for the type of error. For
    `RangeError.prototype.name`, the initial value is `"RangeError"`.



 
Instance methods 
----------------

 
*Inherits instance methods from its parent [`Error`](error)*.



 
Examples
--------


 
### Using RangeError (for numeric values) 

 
 
 
[js]


```js
function check(n) {
  if (!(n >= -500 && n <= 500)) {
    throw new RangeError("The argument must be between -500 and 500.");
  }
}

try {
  check(2000);
} catch (error) {
  if (error instanceof RangeError) {
    // Handle the error
  }
}
```




 
### Using RangeError (for non-numeric values) 

 
 
 
[js]


```js
function check(value) {
  if (!["apple", "banana", "carrot"].includes(value)) {
    throw new RangeError(
      'The argument must be an "apple", "banana", or "carrot".',
    );
  }
}

try {
  check("cabbage");
} catch (error) {
  if (error instanceof RangeError) {
    // Handle the error
  }
}
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-native-error-types-used-in-this-standard-rangeerror]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-native-error-types-used-in-this-standard-rangeerror)

  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


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

`RangeError`

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

`RangeError`

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
-   [`Array`](array)
-   [`Number.prototype.toExponential()`](number/toexponential)
-   [`Number.prototype.toFixed()`](number/tofixed)
-   [`Number.prototype.toPrecision()`](number/toprecision)
-   [`String.prototype.normalize()`](string/normalize)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RangeError>

