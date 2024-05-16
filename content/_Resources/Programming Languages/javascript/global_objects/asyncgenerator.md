AsyncGenerator
==============


The `AsyncGenerator` object is returned by an [async generator
function](../statements/async_function*) and it conforms to both the
[async iterable protocol and the async iterator
protocol](../iteration_protocols#the_async_iterator_and_async_iterable_protocols).

Async generator methods always yield [`Promise`](promise) objects.

`AsyncGenerator` is a subclass of the hidden
[`AsyncIterator`](asynciterator) class.



Try it 
------






Constructor
-----------


The `AsyncGenerator` constructor is not available globally. Instances of
`AsyncGenerator` must be returned from [async generator
functions](../statements/async_function*)



[js]


```js
async function* createAsyncGenerator() {
  yield await Promise.resolve(1);
  yield await Promise.resolve(2);
  yield await Promise.resolve(3);
}
const asyncGen = createAsyncGenerator();
asyncGen.next().then((res) => console.log(res.value)); // 1
asyncGen.next().then((res) => console.log(res.value)); // 2
asyncGen.next().then((res) => console.log(res.value)); // 3
```


In fact, there\'s no JavaScript entity that corresponds to the
`AsyncGenerator` constructor. There\'s only a hidden object which is the
prototype object shared by all objects created by async generator
functions. This object is often stylized as `AsyncGenerator.prototype`
to make it look like a class, but it should be more appropriately called
[`AsyncGeneratorFunction.prototype.prototype`](asyncgeneratorfunction),
because `AsyncGeneratorFunction` is an actual JavaScript entity.




Instance properties 
-------------------


These properties are defined on `AsyncGenerator.prototype` and shared by
all `AsyncGenerator` instances.

[`AsyncGenerator.prototype.constructor`](object/constructor)

:   The constructor function that created the instance object. For
    `AsyncGenerator` instances, the initial value is
    [`AsyncGeneratorFunction.prototype`](asyncgeneratorfunction).

     
    **Note:** `AsyncGenerator` objects do not store a reference to the
    async generator function that created them.
    

[`AsyncGenerator.prototype[@@toStringTag]`](#asyncgenerator.prototypetostringtag)

:   The initial value of the [`@@toStringTag`](symbol/tostringtag)
    property is the string `"AsyncGenerator"`. This property is used in
    [`Object.prototype.toString()`](object/tostring).




Instance methods 
----------------


*Also inherits instance methods from its parent
[`AsyncIterator`](asynciterator)*.

[`AsyncGenerator.prototype.next()`](asyncgenerator/next)

:   Returns a [`Promise`](promise) which will be resolved with the given
    value yielded by the [`yield`](../operators/yield) expression.

[`AsyncGenerator.prototype.return()`](asyncgenerator/return)

:   Acts as if a `return` statement is inserted in the generator\'s body
    at the current suspended position, which finishes the generator and
    allows the generator to perform any cleanup tasks when combined with
    a [`try...finally`](../statements/try...catch#the_finally_block)
    block.

[`AsyncGenerator.prototype.throw()`](asyncgenerator/throw)

:   Acts as if a `throw` statement is inserted in the generator\'s body
    at the current suspended position, which informs the generator of an
    error condition and allows it to handle the error, or perform
    cleanup and close itself.




Examples
--------



### Async generator iteration 


The following example iterates over an async generator, logging values
1--6 to the console at decreasing time intervals. Notice how each time a
Promise is yielded, but it\'s automatically resolved within the
`for await...of` loop.



[js]


```js
// An async task. Pretend it's doing something more useful
// in practice.
function delayedValue(time, value) {
  return new Promise((resolve /*, reject*/) => {
    setTimeout(() => resolve(value), time);
  });
}

async function* generate() {
  yield delayedValue(2000, 1);
  yield delayedValue(100, 2);
  yield delayedValue(500, 3);
  yield delayedValue(250, 4);
  yield delayedValue(125, 5);
  yield delayedValue(50, 6);
  console.log("All done!");
}

async function main() {
  for await (const value of generate()) {
    console.log("value", value);
  }
}

main().catch((e) => console.error(e));
```




Specifications
--------------


  -------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-asyncgenerator-objects]](https://tc39.es/ecma262/multipage/control-abstraction-objects.html#sec-asyncgenerator-objects)

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

`AsyncGenerator`

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

`next`

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

`return`

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

`throw`

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


-   [function\*](../statements/function*)
-   [async function\*](../statements/async_function*)
-   [`function*` expression](../operators/function*)
-   [Generator Function](generatorfunction)
-   [Async Generator Function](asyncgeneratorfunction)
-   [Iterators and
    generators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_generators)
    guide




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/AsyncGenerator>

