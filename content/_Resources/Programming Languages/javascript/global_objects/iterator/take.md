Iterator.prototype.take()
=========================

 
 
**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.


The `take()` method of [`Iterator`](../iterator) instances returns a new
[iterator helper](../iterator#iterator_helpers) that yields the given
number of elements in this iterator and then terminates.


 
Syntax
------

 
 
 
[js]


```js
take(limit)
```




 
### Parameters

 

[`limit`](#limit)

:   The number of elements to take from the start of the iteration.



 
### Return value 

 
A new [iterator helper](../iterator#iterator_helpers). The returned
iterator helper yields the elements in the original iterator one-by-one,
and then completes (the `next()` method produces
`{ value: undefined, done: true }`) once `limit` elements have been
yielded, or when the original iterator is exhausted, whichever comes
first.



 
### Exceptions

 

[`RangeError`](../rangeerror)

:   Thrown if `limit` becomes [`NaN`](../nan) or negative when
    [converted to an integer](../number#integer_conversion).



 
Examples
--------


 
### Using take() 

 
The following example creates an iterator that yields terms in the
Fibonacci sequence, and then logs the first three terms:

 
 
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

const seq = fibonacci().take(3);
console.log(seq.next().value); // 1
console.log(seq.next().value); // 1
console.log(seq.next().value); // 2
console.log(seq.next().value); // undefined
```




 
### Using take() with a for\...of loop 

 
`take()` is most convenient when you are not hand-rolling the iterator.
Because iterators are also iterable, you can iterate the returned helper
with a [`for...of`](../../statements/for...of) loop:

 
 
[js]


```js
for (const n of fibonacci().take(5)) {
  console.log(n);
}

// Logs:
// 1
// 1
// 2
// 3
// 5
```


Because `fibonacci()` is an infinite iterator, you can\'t use a `for`
loop to iterate it directly.



 
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




 
### Lower and upper bounds of take count 

 
When the `limit` is negative or [`NaN`](../nan), a
[`RangeError`](../rangeerror) is thrown:

 
 
[js]


```js
fibonacci().take(-1); // RangeError: -1 must be positive
fibonacci().take(undefined); // RangeError: undefined must be positive
```


When the `limit` is larger than the total number of elements the
iterator can produce (such as [`Infinity`](../infinity)), the returned
iterator helper has essentially the same behavior as the original
iterator:

 
 
[js]


```js
for (const n of new Set([1, 2, 3]).values().take(Infinity)) {
  console.log(n);
}

// Logs:
// 1
// 2
// 3
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------
  [Iterator Helpers\
  [\#
  sec-iteratorprototype.take]](https://tc39.es/proposal-iterator-helpers/#sec-iteratorprototype.take)

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

`take`

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

 
-   [Polyfill of `Iterator.prototype.take` in
    `core-js`](https://github.com/zloirock/core-js#iterator-helpers)
-   [`Iterator`](../iterator)
-   [`Iterator.prototype.drop()`](drop)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Iterator/take>

