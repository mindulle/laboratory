Iterator.prototype.drop()
=========================

 
 
**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.


The `drop()` method of [`Iterator`](../iterator) instances returns a new
[iterator helper](../iterator#iterator_helpers) that skips the given
number of elements at the start of this iterator.


 
Syntax
------

 
 
 
[js]


```js
drop(limit)
```




 
### Parameters

 

[`limit`](#limit)

:   The number of elements to drop from the start of the iteration.



 
### Return value 

 
A new [iterator helper](../iterator#iterator_helpers). The first time
the returned iterator helper\'s `next()` method is called, the current
iterator is immediately advanced by `limit` elements, and then the next
element (the `limit+1`-th element) is yielded. The iterator helper then
yields the remaining elements one-by-one. If the current iterator has
fewer than `limit` elements, the new iterator helper will be immediately
completed the first time `next()` is called.



 
### Exceptions

 

[`RangeError`](../rangeerror)

:   Thrown if `limit` becomes [`NaN`](../nan) or negative when
    [converted to an integer](../number#integer_conversion).



 
Examples
--------


 
### Using drop() 

 
The following example creates an iterator that yields terms in the
Fibonacci sequence, starting from the 3rd term by dropping the first two
terms:

 
 
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

const seq = fibonacci().drop(2);
console.log(seq.next().value); // 2
console.log(seq.next().value); // 3
```


This is equivalent to:

 
 
[js]


```js
const seq = fibonacci();
seq.next();
seq.next();
```




 
### Using drop() with a for\...of loop 

 
`drop()` is most convenient when you are not hand-rolling the iterator.
Because iterators are also iterable, you can iterate the returned helper
with a [`for...of`](../../statements/for...of) loop:

 
 
[js]


```js
for (const n of fibonacci().drop(2)) {
  console.log(n);
  if (n > 30) {
    break;
  }
}

// Logs:
// 2
// 3
// 5
// 8
// 13
// 21
// 34
```




 
### Combining drop() with take() 

 
You can combine `drop()` with [`Iterator.prototype.take()`](take) to get
a slice of an iterator:

 
 
[js]


```js
for (const n of fibonacci().drop(2).take(5)) {
  // Drops the first two elements, then takes the next five
  console.log(n);
}
// Logs:
// 2
// 3
// 5
// 8
// 13

for (const n of fibonacci().take(5).drop(2)) {
  // Takes the first five elements, then drops the first two
  console.log(n);
}
// Logs:
// 2
// 3
// 5
```




 
### Lower and upper bounds of drop count 

 
When the `limit` is negative or [`NaN`](../nan), a
[`RangeError`](../rangeerror) is thrown:

 
 
[js]


```js
fibonacci().drop(-1); // RangeError: -1 must be positive
fibonacci().drop(undefined); // RangeError: undefined must be positive
```


When the `limit` is larger than the total number of elements the
iterator can produce (such as [`Infinity`](../infinity)), the returned
iterator helper will instantly drop all elements and then be completed
the first time `next()` is called. If the current iterator is infinite,
the returned iterator helper will never complete.

 
 
[js]


```js
fibonacci().drop(Infinity).next(); // Never ends
new Set([1, 2, 3]).values().drop(Infinity).next(); // { value: undefined, done: true }
new Set([1, 2, 3]).values().drop(4).next(); // { value: undefined, done: true }
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------
  [Iterator Helpers\
  [\#
  sec-iteratorprototype.drop]](https://tc39.es/proposal-iterator-helpers/#sec-iteratorprototype.drop)

  -------------------------------------------------------------------------------------------------------------


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

`drop`

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

 
-   [Polyfill of `Iterator.prototype.drop` in
    `core-js`](https://github.com/zloirock/core-js#iterator-helpers)
-   [`Iterator`](../iterator)
-   [`Iterator.prototype.take()`](take)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Iterator/drop>

