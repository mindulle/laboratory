RangeError() constructor
========================

 
The `RangeError()` constructor creates [`RangeError`](../rangeerror)
objects.


 
Syntax
------

 
 
 
[js]


```js
new RangeError()
new RangeError(message)
new RangeError(message, options)
new RangeError(message, fileName)
new RangeError(message, fileName, lineNumber)

RangeError()
RangeError(message)
RangeError(message, options)
RangeError(message, fileName)
RangeError(message, fileName, lineNumber)
```


 
**Note:** `RangeError()` can be called with or without
[`new`](../../operators/new). Both create a new `RangeError` instance.




 
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

 
See also 
--------

 
-   [`Error`](../error)
-   [`Array`](../array)
-   [`Number.prototype.toExponential()`](../number/toexponential)
-   [`Number.prototype.toFixed()`](../number/tofixed)
-   [`Number.prototype.toPrecision()`](../number/toprecision)
-   [`String.prototype.normalize()`](../string/normalize)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RangeError/RangeError>

