AggregateError
==============


The `AggregateError` object represents an error when several errors need
to be wrapped in a single error. It is thrown when multiple errors need
to be reported by an operation, for example by
[`Promise.any()`](promise/any), when all promises passed to it reject.

`AggregateError` is a subclass of [`Error`](error).



Constructor
-----------



[`AggregateError()`](aggregateerror/aggregateerror)

:   Creates a new `AggregateError` object.




Instance properties 
-------------------


*Also inherits instance properties from its parent [`Error`](error)*.

These properties are defined on `AggregateError.prototype` and shared by
all `AggregateError` instances.

[`AggregateError.prototype.constructor`](object/constructor)

:   The constructor function that created the instance object. For
    `AggregateError` instances, the initial value is the
    [`AggregateError`](aggregateerror/aggregateerror) constructor.

[`AggregateError.prototype.name`](error/name)

:   Represents the name for the type of error. For
    `AggregateError.prototype.name`, the initial value is
    `"AggregateError"`.

These properties are own properties of each `AggregateError` instance.

[`errors`](aggregateerror/errors)

:   An array representing the errors that were aggregated.




Instance methods 
----------------


*Inherits instance methods from its parent [`Error`](error)*.




Examples
--------



### Catching an AggregateError 




[js]


```js
Promise.any([Promise.reject(new Error("some error"))]).catch((e) => {
  console.log(e instanceof AggregateError); // true
  console.log(e.message); // "All Promises rejected"
  console.log(e.name); // "AggregateError"
  console.log(e.errors); // [ Error: "some error" ]
});
```





### Creating an AggregateError 




[js]


```js
try {
  throw new AggregateError([new Error("some error")], "Hello");
} catch (e) {
  console.log(e instanceof AggregateError); // true
  console.log(e.message); // "Hello"
  console.log(e.name); // "AggregateError"
  console.log(e.errors); // [ Error: "some error" ]
}
```




Specifications
--------------


  -------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-aggregate-error-objects]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-aggregate-error-objects)

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

`AggregateError`

85

85

79

71

14

85

79

60

14

14.0

85

1.2

15.0.0

`AggregateError`

85

85

79

71

14

85

79

60

14

14.0

85

1.2

15.0.0

`errors`

85

85

79

71

14

85

79

60

14

14.0

85

1.2

15.0.0

`serializable_object`

No

No

103Serialized properties: `name`, `message`, `cause`, `errors`.

No

No

No

103Serialized properties: `name`, `message`, `cause`, `errors`.

No

No

No

No

No

No


See also 
--------


-   [Polyfill of `AggregateError` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-promise)
-   [`Error`](error)
-   [`Promise.any`](promise/any)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/AggregateError>

