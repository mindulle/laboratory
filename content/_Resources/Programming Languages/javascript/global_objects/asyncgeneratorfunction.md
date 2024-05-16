AsyncGeneratorFunction
======================


The `AsyncGeneratorFunction` object provides methods for [async
generator functions](../statements/async_function*). In JavaScript,
every async generator function is actually an `AsyncGeneratorFunction`
object.

Note that `AsyncGeneratorFunction` is *not* a global object. It can be
obtained with the following code:



[js]


```js
const AsyncGeneratorFunction = async function* () {}.constructor;
```


`AsyncGeneratorFunction` is a subclass of [`Function`](function).



Try it 
------






Constructor
-----------



[`AsyncGeneratorFunction()`](asyncgeneratorfunction/asyncgeneratorfunction)

:   Creates a new `AsyncGeneratorFunction` object.




Instance properties 
-------------------


*Also inherits instance properties from its parent
[`Function`](function)*.

These properties are defined on `AsyncGeneratorFunction.prototype` and
shared by all `AsyncGeneratorFunction` instances.

[`AsyncGeneratorFunction.prototype.constructor`](object/constructor)

:   The constructor function that created the instance object. For
    `AsyncGeneratorFunction` instances, the initial value is the
    [`AsyncGeneratorFunction`](asyncgeneratorfunction/asyncgeneratorfunction)
    constructor.

[`AsyncGeneratorFunction.prototype.prototype`](#asyncgeneratorfunction.prototype.prototype)

:   All async generator functions share the same
    [`prototype`](function/prototype) property, which is
    [`AsyncGenerator.prototype`](asyncgenerator). Each async generator
    function instance also has its own `prototype` property. When the
    async generator function is called, the returned async generator
    object inherits from the async generator function\'s `prototype`
    property, which in turn inherits from
    `AsyncGeneratorFunction.prototype.prototype`.

[`AsyncGeneratorFunction.prototype[@@toStringTag]`](#asyncgeneratorfunction.prototypetostringtag)

:   The initial value of the [`@@toStringTag`](symbol/tostringtag)
    property is the string `"AsyncGeneratorFunction"`. This property is
    used in [`Object.prototype.toString()`](object/tostring).




Instance methods 
----------------


*Inherits instance methods from its parent [`Function`](function)*.



Specifications
--------------


  -----------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-asyncgeneratorfunction-objects]](https://tc39.es/ecma262/multipage/control-abstraction-objects.html#sec-asyncgeneratorfunction-objects)

  -----------------------------------------------------------------------------------------------------------------------------------------------------


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


-   [`async function*`](../statements/async_function*)
-   [`async function*` expression](../operators/async_function*)
-   [`Function`](function)
-   [`AsyncFunction`](asyncfunction)
-   [`GeneratorFunction`](generatorfunction)
-   [Functions](../functions)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/AsyncGeneratorFunction>

