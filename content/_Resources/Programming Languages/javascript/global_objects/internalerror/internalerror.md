InternalError() constructor
===========================

 
 
**Non-standard:** This feature is non-standard and is not on a standards
track. Do not use it on production sites facing the Web: it will not
work for every user. There may also be large incompatibilities between
implementations and the behavior may change in the future.


The `InternalError()` constructor creates
[`InternalError`](../internalerror) objects.


 
Syntax
------

 
 
 
[js]


```js
new InternalError()
new InternalError(message)
new InternalError(message, options)
new InternalError(message, fileName)
new InternalError(message, fileName, lineNumber)

InternalError()
InternalError(message)
InternalError(message, options)
InternalError(message, fileName)
InternalError(message, fileName, lineNumber)
```


 
**Note:** `InternalError()` can be called with or without
[`new`](../../operators/new). Both create a new `InternalError`
instance.




 
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


 
### Creating a new InternalError 

 
 
 
[js]


```js
new InternalError("Engine failure");
```




 
Specifications
--------------

 
Not part of any standard.



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

`InternalError`

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

 
See also 
--------

 
-   [`Error`](../error)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/InternalError/InternalError>

