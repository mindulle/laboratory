Error() constructor
===================

 
The `Error()` constructor creates [`Error`](../error) objects.


 
Syntax
------

 
 
 
[js]


```js
new Error()
new Error(message)
new Error(message, options)
new Error(message, fileName)
new Error(message, fileName, lineNumber)

Error()
Error(message)
Error(message, options)
Error(message, fileName)
Error(message, fileName, lineNumber)
```


 
**Note:** `Error()` can be called with or without
[`new`](../../operators/new). Both create a new `Error` instance.




 
### Parameters

 

[`message`](#message) [Optional]

:   A human-readable description of the error.

[`options`](#options) [Optional]

:   An object that has the following properties:

    [`cause`](#cause) [Optional]

    :   A value indicating the specific cause of the error, reflected in
        the [`cause`](cause) property. When catching and re-throwing an
        error with a more-specific or useful error message, this
        property can be used to pass the original error.

[`fileName`](#filename) [Optional]

:   The path to the file that raised this error, reflected in the
    [`fileName`](filename) property. Defaults to the name of the file
    containing the code that called the `Error()` constructor.

[`lineNumber`](#linenumber) [Optional]

:   The line number within the file on which the error was raised,
    reflected in the [`lineNumber`](linenumber) property. Defaults to
    the line number containing the `Error()` constructor invocation.



 
Examples
--------


 
### Function call or new construction 

 
When `Error` is used like a function, that is without
[`new`](../../operators/new), it will return an `Error` object.
Therefore, a mere call to `Error` will produce the same output that
constructing an `Error` object via the `new` keyword would.

 
 
[js]


```js
const x = Error("I was created using a function call!");

// above has the same functionality as following
const y = new Error('I was constructed via the "new" keyword!');
```




 
### Rethrowing an error with a cause 

 
It is sometimes useful to catch an error and re-throw it with a new
message. In this case you should pass the original error into the
constructor for the new `Error`, as shown.

 
 
[js]


```js
try {
  frameworkThatCanThrow();
} catch (err) {
  throw new Error("New error message", { cause: err });
}
```


For a more detailed example see [Error \> Differentiate between similar
errors](../error#differentiate_between_similar_errors).



 
### Omitting options argument 

 
JavaScript only tries to read `options.cause` if `options` is an object
--- this avoids ambiguity with the other non-standard
`Error(message, fileName, lineNumber)` signature, which requires the
second parameter to be a string. If you omit `options`, pass a primitive
value as `options`, or pass an object without the `cause` property, then
the created `Error` object will have no `cause` property.

 
 
[js]


```js
// Omitting options
const error1 = new Error("Error message");
console.log("cause" in error1); // false

// Passing a primitive value
const error2 = new Error("Error message", "");
console.log("cause" in error2); // false

// Passing an object without a cause property
const error3 = new Error("Error message", { details: "http error" });
console.log("cause" in error3); // false
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-error-constructor]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-error-constructor)

  -------------------------------------------------------------------------------------------------------------------


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

`Error`

1

12

1

4

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`fileName_parameter`

No

No

1

No

No

No

4

No

No

No

No

No

No

`lineNumber_parameter`

No

No

1

No

No

No

4

No

No

No

No

No

No

`options_cause_parameter`

93

93

91

79

15

93

91

66

15

17.0

93

1.13

16.9.0

 
See also 
--------

 
-   [Polyfill of `Error` with `cause` support in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-error)
-   [`throw`](../../statements/throw)
-   [`try...catch`](../../statements/try...catch)
-   [Error causes](https://v8.dev/features/error-cause) on v8.dev (2021)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error/Error>

