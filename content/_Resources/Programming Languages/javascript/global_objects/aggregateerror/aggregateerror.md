AggregateError() constructor
============================

 
The `AggregateError()` constructor creates
[`AggregateError`](../aggregateerror) objects.


 
Syntax
------

 
 
 
[js]


```js
new AggregateError(errors)
new AggregateError(errors, message)
new AggregateError(errors, message, options)

AggregateError(errors)
AggregateError(errors, message)
AggregateError(errors, message, options)
```


 
**Note:** `AggregateError()` can be called with or without
[`new`](../../operators/new). Both create a new `AggregateError`
instance.




 
### Parameters

 

[`errors`](#errors)

:   An iterable of errors, may not actually be [`Error`](../error)
    instances.

[`message`](#message) [Optional]

:   An optional human-readable description of the aggregate error.

[`options`](#options) [Optional]

:   An object that has the following properties:

    [`cause`](#cause) [Optional]

    :   A property indicating the specific cause of the error. When
        catching and re-throwing an error with a more-specific or useful
        error message, this property can be used to pass the original
        error.



 
Examples
--------


 
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

 
  ---------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-aggregate-error-constructor]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-aggregate-error-constructor)

  ---------------------------------------------------------------------------------------------------------------------------------------


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

 
See also 
--------

 
-   [Polyfill of `AggregateError` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-promise)
-   [`Promise.any`](../promise/any)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/AggregateError/AggregateError>

