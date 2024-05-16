AsyncFunction() constructor
===========================

Baseline [Widely available]
--------------------------------------


This feature is well established and works across many devices and
browser versions. It's been available across browsers since April 2017.

-   [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-evolution-on-mdn/)
-   [See full compatibility](#browser_compatibility)
-   [Report
    feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FJavaScript%2FReference%2FGlobal_Objects%2FAsyncFunction%2FAsyncFunction&level=high)



The `AsyncFunction()` constructor creates
[`AsyncFunction`](../asyncfunction) objects.

Note that `AsyncFunction` is *not* a global object. It can be obtained
with the following code:



[js]


```js
const AsyncFunction = async function () {}.constructor;
```


The `AsyncFunction()` constructor is not intended to be used directly,
and all caveats mentioned in the [`Function()`](../function/function)
description apply to `AsyncFunction()`.



Syntax
------




[js]


```js
new AsyncFunction(functionBody)
new AsyncFunction(arg1, functionBody)
new AsyncFunction(arg1, arg2, functionBody)
new AsyncFunction(arg1, arg2, /* …, */ argN, functionBody)

AsyncFunction(functionBody)
AsyncFunction(arg1, functionBody)
AsyncFunction(arg1, arg2, functionBody)
AsyncFunction(arg1, arg2, /* …, */ argN, functionBody)
```


 
**Note:** `AsyncFunction()` can be called with or without
[`new`](../../operators/new). Both create a new `AsyncFunction`
instance.





### Parameters


See [`Function()`](../function/function).




Examples
--------



### Creating an async function from an AsyncFunction() constructor 




[js]


```js
function resolveAfter2Seconds(x) {
  return new Promise((resolve) => {
    setTimeout(() => {
      resolve(x);
    }, 2000);
  });
}

const AsyncFunction = async function () {}.constructor;

const fn = new AsyncFunction(
  "a",
  "b",
  "return await resolveAfter2Seconds(a) + await resolveAfter2Seconds(b);",
);

fn(10, 20).then((v) => {
  console.log(v); // prints 30 after 4 seconds
});
```




Specifications
--------------


  ---------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-async-function-constructor]](https://tc39.es/ecma262/multipage/control-abstraction-objects.html#sec-async-function-constructor)

  ---------------------------------------------------------------------------------------------------------------------------------------------


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


See also 
--------


-   [`async function`](../../statements/async_function)
-   [`async function` expression](../../operators/async_function)
-   [`Function()` constructor](../function/function)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/AsyncFunction/AsyncFunction>

