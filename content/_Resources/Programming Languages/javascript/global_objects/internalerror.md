InternalError
=============

 
 
**Non-standard:** This feature is non-standard and is not on a standards
track. Do not use it on production sites facing the Web: it will not
work for every user. There may also be large incompatibilities between
implementations and the behavior may change in the future.


The `InternalError` object indicates an error that occurred internally
in the JavaScript engine.

Example cases are mostly when something is too large, e.g.:

-   \"too many switch cases\",
-   \"too many parentheses in regular expression\",
-   \"array initializer too large\",
-   \"too much recursion\".

`InternalError` is a subclass of [`Error`](error).


 
Constructor
-----------

 

[`InternalError()`](internalerror/internalerror) [Non-standard]

:   Creates a new `InternalError` object.



 
Instance properties 
-------------------

 
*Also inherits instance properties from its parent [`Error`](error)*.

These properties are defined on `InternalError.prototype` and shared by
all `InternalError` instances.

[`InternalError.prototype.constructor`](object/constructor)

:   The constructor function that created the instance object. For
    `InternalError` instances, the initial value is the
    [`InternalError`](internalerror/internalerror) constructor.

[`InternalError.prototype.name`](error/name)

:   Represents the name for the type of error. For
    `InternalError.prototype.name`, the initial value is
    `"InternalError"`.



 
Instance methods 
----------------

 
*Inherits instance methods from its parent [`Error`](error)*.



 
Examples
--------


 
### Too much recursion 

 
This recursive function runs 10 times, as per the exit condition.

 
 
[js]


```js
function loop(x) {
  // "x >= 10" is the exit condition
  if (x >= 10) return;

  // do stuff
  loop(x + 1); // the recursive call
}
loop(0);
```


Setting this condition to an extremely high value, may not work:

 
 
[js]


```js
function loop(x) {
  if (x >= 1000000000000) return;

  // do stuff
  loop(x + 1);
}
loop(0);

// InternalError: too much recursion
```


For more information, see [InternalError: too much
recursion.](../errors/too_much_recursion)



 
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

 
-   [`Error`](error)
-   [InternalError: too much recursion](../errors/too_much_recursion)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/InternalError>

