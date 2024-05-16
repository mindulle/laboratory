Iterator.prototype.flatMap()
============================

 
 
**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.


The `flatMap()` method of [`Iterator`](../iterator) instances returns a
new [iterator helper](../iterator#iterator_helpers) that takes each
element in the original iterator, runs it through a mapping function,
and yields elements returned by the mapping function (which are
contained in another iterator or iterable).


 
Syntax
------

 
 
 
[js]


```js
flatMap(callbackFn)
```




 
### Parameters

 

[`callbackFn`](#callbackfn)

:   A function to execute for each element produced by the iterator. It
    should return an iterator or iterable that yields elements to be
    yielded by `flatMap()`, or a single non-iterator/iterable value to
    be yielded. The function is called with the following arguments:

    [`element`](#element)

    :   The current element being processed in the array.

    [`index`](#index)

    :   The index of the current element being processed in the array.



 
### Return value 

 
A new [iterator helper](../iterator#iterator_helpers). The first time
the iterator helper\'s `next()` method is called, it calls `callbackFn`
on the first element produced by the underlying iterator, and the return
value, which should be an iterator or iterable, is yielded one-by-one by
the iterator helper (like [`yield*`](../../operators/yield*)). The next
element is fetched from the underlying iterator when the previous one
returned by `callbackFn` is completed. When the underlying iterator is
completed, the iterator helper is also completed (the `next()` method
produces `{ value: undefined, done: true }`).



 
### Exceptions

 

[`TypeError`](../typeerror)

:   Thrown if `callbackFn` returns a non-iterator/iterable value or a
    string primitive.



 
Description
-----------

 
`flatMap` accepts two kinds of return values from `callbackFn`: an
iterator or iterable. They are handled in the same way as
[`Iterator.from()`](from): if the return value is iterable, the
`@@iterator` method is called and the return value is used; otherwise,
the return value is treated as an iterator and its `next()` method is
called.

 
 
[js]


```js
[1, 2, 3]
  .values()
  .flatMap((x) => {
    let itDone = false;
    const it = {
      next() {
        if (itDone) {
          return { value: undefined, done: true };
        }
        itDone = true;
        return { value: x, done: false };
      },
    };
    switch (x) {
      case 1:
        // An iterable that's not an iterator
        return { [Symbol.iterator]: () => it };
      case 2:
        // An iterator that's not an iterable
        return it;
      case 3:
        // An iterable iterator is treated as an iterable
        return {
          ...it,
          [Symbol.iterator]() {
            console.log("@@iterator called");
            return it;
          },
        };
    }
  })
  .toArray();
// Logs "@@iterator called"
// Returns [1, 2, 3]
```




 
Examples
--------


 
### Merging maps 

 
The following example merges two [`Map`](../map) objects into one:

 
 
[js]


```js
const map1 = new Map([
  ["a", 1],
  ["b", 2],
  ["c", 3],
]);
const map2 = new Map([
  ["d", 4],
  ["e", 5],
  ["f", 6],
]);

const merged = new Map([map1, map2].values().flatMap((x) => x));
console.log(merged.get("a")); // 1
console.log(merged.get("e")); // 5
```


This avoids creating any temporary copies of the map\'s content. Note
that the array `[map1, map2]` must first be converted to an iterator
(using [`Array.prototype.values()`](../array/values)), because
[`Array.prototype.flatMap()`](../array/flatmap) only flattens arrays,
not iterables.

 
 
[js]


```js
new Map([map1, map2].flatMap((x) => x)); // Map(1) {undefined => undefined}
```




 
### Returning strings 

 
Strings are iterable, but `flatMap()` specifically rejects string
primitives returned from `callbackFn`, this is because the behavior of
iterating by code points is often not what you want.

 
 
[js]


```js
[1, 2, 3]
  .values()
  .flatMap((x) => String(x))
  .toArray(); // TypeError: Iterator.prototype.flatMap called on non-object
```


You may want to wrap it in an array instead so the entire string is
yielded as one:

 
 
[js]


```js
[1, 2, 3]
  .values()
  .flatMap((x) => [String(x)])
  .toArray(); // ['1', '2', '3']
```


Or, if the behavior of iterating by code points is intended, you can use
[`Iterator.from()`](from) to convert it to a proper iterator:

 
 
[js]


```js
[1, 2, 3]
  .values()
  .flatMap((x) => Iterator.from(String(x * 10)))
  .toArray();
// ['1', '0', '2', '0', '3', '0']
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------
  [Iterator Helpers\
  [\#
  sec-iteratorprototype.flatmap]](https://tc39.es/proposal-iterator-helpers/#sec-iteratorprototype.flatmap)

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

`flatMap`

117

117

No

103

No

117

No

78

No

No

117

No

No

 
See also 
--------

 
-   [Polyfill of `Iterator.prototype.flatMap` in
    `core-js`](https://github.com/zloirock/core-js#iterator-helpers)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Iterator/flatMap>

