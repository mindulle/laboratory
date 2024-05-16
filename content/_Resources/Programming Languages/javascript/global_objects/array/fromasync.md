Array.fromAsync()
=================


The `Array.fromAsync()` static method creates a new, shallow-copied
`Array` instance from an [async
iterable](../../iteration_protocols#the_async_iterator_and_async_iterable_protocols),
[iterable](../../iteration_protocols#the_iterable_protocol), or
[array-like](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections#working_with_array-like_objects)
object.



Syntax
------




[js]


```js
Array.fromAsync(arrayLike)
Array.fromAsync(arrayLike, mapFn)
Array.fromAsync(arrayLike, mapFn, thisArg)
```





### Parameters



[`arrayLike`](#arraylike)

:   An async iterable, iterable, or array-like object to convert to an
    array.

[`mapFn`](#mapfn) [Optional]

:   A function to call on every element of the array. If provided, every
    value to be added to the array is first passed through this
    function, and `mapFn`\'s return value is added to the array instead
    (after being [awaited](../../operators/await)). The function is
    called with the following arguments:

    [`element`](#element)

    :   The current element being processed in the array. Because all
        elements are first [awaited](../../operators/await), this value
        will never be a [thenable](../promise#thenables).

    [`index`](#index)

    :   The index of the current element being processed in the array.

[`thisArg`](#thisarg) [Optional]

:   Value to use as `this` when executing `mapFn`.




### Return value 


A new [`Promise`](../promise) whose fulfillment value is a new
[`Array`](../array) instance.




Description
-----------


`Array.fromAsync()` lets you create arrays from:

-   [async iterable
    objects](../../iteration_protocols#the_async_iterator_and_async_iterable_protocols)
    (objects such as
    [`ReadableStream`](https://developer.mozilla.org/en-US/docs/Web/API/ReadableStream)
    and [`AsyncGenerator`](../asyncgenerator)); or, if the object is not
    async iterable,
-   [iterable objects](../../iteration_protocols#the_iterable_protocol)
    (objects such as [`Map`](../map) and [`Set`](../set)); or, if the
    object is not iterable,
-   array-like objects (objects with a `length` property and indexed
    elements).

`Array.fromAsync()` iterates the async iterable in a fashion very
similar to [`for await...of`](../../statements/for-await...of).
`Array.fromAsync()` is almost equivalent to [`Array.from()`](from) in
terms of behavior, except the following:

-   `Array.fromAsync()` handles async iterable objects.
-   `Array.fromAsync()` returns a [`Promise`](../promise) that fulfills
    to the array instance.
-   If `Array.fromAsync()` is called with a non-async iterable object,
    each element to be added to the array is first
    [awaited](../../operators/await).
-   If a `mapFn` is provided, its input and output are internally
    awaited.

`Array.fromAsync()` and [`Promise.all()`](../promise/all) can both turn
an iterable of promises into a promise of an array. However, there are
two key differences:

-   `Array.fromAsync()` awaits each value yielded from the object
    sequentially. `Promise.all()` awaits all values concurrently.
-   `Array.fromAsync()` iterates the iterable lazily, and doesn\'t
    retrieve the next value until the current one is settled.
    `Promise.all()` retrieves all values in advance and awaits them all.




Examples
--------



### Array from an async iterable 




[js]


```js
const asyncIterable = (async function* () {
  for (let i = 0; i < 5; i++) {
    await new Promise((resolve) => setTimeout(resolve, 10 * i));
    yield i;
  }
})();

Array.fromAsync(asyncIterable).then((array) => console.log(array));
// [0, 1, 2, 3, 4]
```





### Array from a sync iterable 




[js]


```js
Array.fromAsync(
  new Map([
    [1, 2],
    [3, 4],
  ]),
).then((array) => console.log(array));
// [[1, 2], [3, 4]]
```





### Array from a sync iterable that yields promises 




[js]


```js
Array.fromAsync(
  new Set([Promise.resolve(1), Promise.resolve(2), Promise.resolve(3)]),
).then((array) => console.log(array));
// [1, 2, 3]
```





### Array from an array-like object of promises 




[js]


```js
Array.fromAsync({
  length: 3,
  0: Promise.resolve(1),
  1: Promise.resolve(2),
  2: Promise.resolve(3),
}).then((array) => console.log(array));
// [1, 2, 3]
```





### Using mapFn 


Both the input and output of `mapFn` are awaited internally by
`Array.fromAsync()`.



[js]


```js
function delayedValue(v) {
  return new Promise((resolve) => setTimeout(() => resolve(v), 100));
}

Array.fromAsync(
  [delayedValue(1), delayedValue(2), delayedValue(3)],
  (element) => delayedValue(element * 2),
).then((array) => console.log(array));
// [2, 4, 6]
```





### Comparison with Promise.all() 


`Array.fromAsync()` awaits each value yielded from the object
sequentially. `Promise.all()` awaits all values concurrently.



[js]


```js
function* makeIterableOfPromises() {
  for (let i = 0; i < 5; i++) {
    yield new Promise((resolve) => setTimeout(resolve, 100));
  }
}

(async () => {
  console.time("Array.fromAsync() time");
  await Array.fromAsync(makeIterableOfPromises());
  console.timeEnd("Array.fromAsync() time");
  // Array.fromAsync() time: 503.610ms

  console.time("Promise.all() time");
  await Promise.all(makeIterableOfPromises());
  console.timeEnd("Promise.all() time");
  // Promise.all() time: 101.728ms
})();
```





### No error handling for sync iterables 


Similar to
[`for await...of`](../../statements/for-await...of#iterating_over_sync_iterables_and_generators),
if the object being iterated is a sync iterable, and an error is thrown
while iterating, the `return()` method of the underlying iterator will
not be called, so the iterator is not closed.



[js]


```js
function* generatorWithRejectedPromises() {
  try {
    yield 0;
    yield Promise.reject(3);
  } finally {
    console.log("called finally");
  }
}

(async () => {
  try {
    await Array.fromAsync(generatorWithRejectedPromises());
  } catch (e) {
    console.log("caught", e);
  }
})();
// caught 3
// No "called finally" message
```


If you need to close the iterator, you need to use a
[`for...of`](../../statements/for...of) loop instead, and `await` each
value yourself.



[js]


```js
(async () => {
  const arr = [];
  try {
    for (const val of generatorWithRejectedPromises()) {
      arr.push(await val);
    }
  } catch (e) {
    console.log("caught", e);
  }
})();
// called finally
// caught 3
```




Specifications
--------------


  -----------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------
  [ES Array.fromAsync (2022)\
  [\#
  sec-array.fromAsync]](https://tc39.es/proposal-array-from-async/#sec-array.fromAsync)

  -----------------------------------------------------------------------------------------------


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

`fromAsync`

121

121

115

No

16.4

121

115

No

16.4

No

121

1.38

No


See also 
--------


-   [Polyfill of `Array.fromAsync` in
    `core-js`](https://github.com/zloirock/core-js#arrayfromasync)
-   [Indexed
    collections](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections)
    guide
-   [`Array`](../array)
-   [`Array()`](array)
-   [`Array.of()`](of)
-   [`Array.from()`](from)
-   [`for await...of`](../../statements/for-await...of)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/fromAsync>

