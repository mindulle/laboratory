AsyncFunction
=============

Baseline [Widely available]
--------------------------------------


This feature is well established and works across many devices and
browser versions. It's been available across browsers since April 2017.

-   [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-evolution-on-mdn/)
-   [See full compatibility](#browser_compatibility)
-   [Report
    feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FJavaScript%2FReference%2FGlobal_Objects%2FAsyncFunction&level=high)



The `AsyncFunction` object provides methods for [async
functions](../statements/async_function). In JavaScript, every async
function is actually an `AsyncFunction` object.

Note that `AsyncFunction` is *not* a global object. It can be obtained
with the following code:



[js]


```js
const AsyncFunction = async function () {}.constructor;
```


`AsyncFunction` is a subclass of [`Function`](function).



Constructor
-----------



[`AsyncFunction()`](asyncfunction/asyncfunction)

:   Creates a new `AsyncFunction` object.




Instance properties 
-------------------


*Also inherits instance properties from its parent
[`Function`](function)*.

These properties are defined on `AsyncFunction.prototype` and shared by
all `AsyncFunction` instances.

[`AsyncFunction.prototype.constructor`](object/constructor)

:   The constructor function that created the instance object. For
    `AsyncFunction` instances, the initial value is the
    [`AsyncFunction`](asyncfunction/asyncfunction) constructor.

[`AsyncFunction.prototype[@@toStringTag]`](#asyncfunction.prototypetostringtag)

:   The initial value of the [`@@toStringTag`](symbol/tostringtag)
    property is the string `"AsyncFunction"`. This property is used in
    [`Object.prototype.toString()`](object/tostring).

 
**Note:** `AsyncFunction` instances do not have the
[`prototype`](function/prototype) property.





Instance methods 
----------------


*Inherits instance methods from its parent [`Function`](function)*.



Specifications
--------------


  -------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-async-function-objects]](https://tc39.es/ecma262/multipage/control-abstraction-objects.html#sec-async-function-objects)

  -------------------------------------------------------------------------------------------------------------------------------------


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

`AsyncFunction`

55

15

52

42

10.1

55

52

42

10.3

6.0

55

1.0

7.6.0

`AsyncFunction`

55

15

52

42

10.1

55

52

42

10.3

6.0

55

1.0

7.6.0


See also 
--------


-   [`async function`](../statements/async_function)
-   [`async function` expression](../operators/async_function)
-   [`Function`](function)
-   [`AsyncGeneratorFunction`](asyncgeneratorfunction)
-   [`GeneratorFunction`](generatorfunction)
-   [Functions](../functions)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/AsyncFunction>

