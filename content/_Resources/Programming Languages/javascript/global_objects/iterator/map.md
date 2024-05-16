Iterator.prototype.map()
========================

 
 
**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.


The `map()` method of [`Iterator`](../iterator) instances returns a new
[iterator helper](../iterator#iterator_helpers) that yields elements of
the iterator, each transformed by a mapping function.


 
Syntax
------

 
 
 
[js]


```js
map(callbackFn)
```




 
### Parameters

 

[`callbackFn`](#callbackfn)

:   A function to execute for each element produced by the iterator. Its
    return value is yielded by the iterator helper. The function is
    called with the following arguments:

    [`element`](#element)

    :   The current element being processed.

    [`index`](#index)

    :   The index of the current element being processed.



 
### Return value 

 
A new [iterator helper](../iterator#iterator_helpers). Each time the
iterator helper\'s `next()` method is called, it gets the next element
from the underlying iterator, applies `callbackFn`, and yields the
return value. When the underlying iterator is completed, the iterator
helper is also completed (the `next()` method produces
`{ value: undefined, done: true }`).



 
Description
-----------

 
The main advantage of iterator helpers over array methods is their
ability to work with infinite iterators. With infinite iterators,
`map()` allows you to create a new iterator that, when iterated,
produces transformed elements.



 
Examples
--------


 
### Using map() 

 
The following example creates an iterator that yields terms in the
Fibonacci sequence, transforms it into a new sequence with each term
squared, and then reads the first few terms:

 
 
[js]


```js
function* fibonacci() {
  let current = 1;
  let next = 1;
  while (true) {
    yield current;
    [current, next] = [next, current + next];
  }
}

const seq = fibonacci().map((x) => x ** 2);
console.log(seq.next().value); // 1
console.log(seq.next().value); // 1
console.log(seq.next().value); // 4
```




 
### Using map() with a for\...of loop 

 
`map()` is most convenient when you are not hand-rolling the iterator.
Because iterators are also iterable, you can iterate the returned helper
with a [`for...of`](../../statements/for...of) loop:

 
 
[js]


```js
for (const n of fibonacci().map((x) => x ** 2)) {
  console.log(n);
  if (n > 30) {
    break;
  }
}

// Logs:
// 1
// 1
// 4
// 9
// 25
// 64
```


This is equivalent to:

 
 
[js]


```js
for (const n of fibonacci()) {
  const n2 = n ** 2;
  console.log(n2);
  if (n2 > 30) {
    break;
  }
}
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------
  [Iterator Helpers\
  [\#
  sec-iteratorprototype.map]](https://tc39.es/proposal-iterator-helpers/#sec-iteratorprototype.map)

  -----------------------------------------------------------------------------------------------------------


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

`map`

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

 
-   [Polyfill of `Iterator.prototype.map` in
    `core-js`](https://github.com/zloirock/core-js#iterator-helpers)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Iterator/map>

