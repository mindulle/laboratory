AsyncGeneratorFunction() constructor
====================================


The `AsyncGeneratorFunction()` constructor creates
[`AsyncGeneratorFunction`](../asyncgeneratorfunction) objects.

Note that `AsyncGeneratorFunction` is not a global object. It could be
obtained by evaluating the following code.



[js]


```js
const AsyncGeneratorFunction = async function* () {}.constructor;
```


The `AsyncGeneratorFunction()` constructor is not intended to be used
directly, and all caveats mentioned in the
[`Function()`](../function/function) description apply to
`AsyncGeneratorFunction()`.



Syntax
------




[js]


```js
new AsyncGeneratorFunction(functionBody)
new AsyncGeneratorFunction(arg1, functionBody)
new AsyncGeneratorFunction(arg1, arg2, functionBody)
new AsyncGeneratorFunction(arg1, arg2, /* …, */ argN, functionBody)

AsyncGeneratorFunction(functionBody)
AsyncGeneratorFunction(arg1, functionBody)
AsyncGeneratorFunction(arg1, arg2, functionBody)
AsyncGeneratorFunction(arg1, arg2, /* …, */ argN, functionBody)
```


 
**Note:** `AsyncGeneratorFunction()` can be called with or without
[`new`](../../operators/new). Both create a new `AsyncGeneratorFunction`
instance.





### Parameters


See [`Function()`](../function/function).




Examples
--------



### Using the constructor 


The following example uses the `AsyncGeneratorFunction` constructor to
create an async generator function.



[js]


```js
const AsyncGeneratorFunction = async function* () {}.constructor;
const createAsyncGenerator = new AsyncGeneratorFunction("a", "yield a * 2");
const asyncGen = createAsyncGenerator(10);
asyncGen.next().then((res) => console.log(res.value)); // 20
```




Specifications
--------------


  -------------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-asyncgeneratorfunction-constructor]](https://tc39.es/ecma262/multipage/control-abstraction-objects.html#sec-asyncgeneratorfunction-constructor)

  -------------------------------------------------------------------------------------------------------------------------------------------------------------


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

`AsyncGeneratorFunction`

63

79

55

50

12

63

55

46

12

8.0

63

1.0

10.0.0


See also 
--------


-   [`async function*`](../../statements/async_function*)
-   [`async function*` expression](../../operators/async_function*)
-   [`Function()` constructor](../function/function)
-   [Iterators and
    generators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_generators)
    guide
-   [Functions](../../functions)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/AsyncGeneratorFunction/AsyncGeneratorFunction>

