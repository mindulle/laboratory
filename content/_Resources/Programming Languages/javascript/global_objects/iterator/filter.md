Iterator.prototype.filter()
===========================

 
 
**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.


The `filter()` method of [`Iterator`](../iterator) instances returns a
new [iterator helper](../iterator#iterator_helpers) that yields only
those elements of the iterator for which the provided callback function
returns `true`.


 
Syntax
------

 
 
 
[js]


```js
filter(callbackFn)
```




 
### Parameters

 

[`callbackFn`](#callbackfn)

:   A function to execute for each element produced by the iterator. It
    should return a
    [truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy)
    value to make the element yielded by the iterator helper, and a
    [falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy)
    value otherwise. The function is called with the following
    arguments:

    [`element`](#element)

    :   The current element being processed.

    [`index`](#index)

    :   The index of the current element being processed.



 
### Return value 

 
A new [iterator helper](../iterator#iterator_helpers). Each time the
iterator helper\'s `next()` method is called, it returns the next
element in the iterator for which the callback function returns `true`.
When the underlying iterator is completed, the iterator helper is also
completed (the `next()` method produces
`{ value: undefined, done: true }`).



 
Description
-----------

 
The main advantage of iterator helpers over array methods is their
ability to work with infinite iterators. With infinite iterators,
`filter()` allows you to iterate over only those elements that satisfy a
given condition.



 
Examples
--------


 
### Using filter() 

 
The following example creates an iterator that yields terms in the
Fibonacci sequence, and then reads the first few terms that are even:

 
 
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

const seq = fibonacci().filter((x) => x % 2 === 0);
console.log(seq.next().value); // 2
console.log(seq.next().value); // 8
console.log(seq.next().value); // 34
```




 
### Using filter() with a for\...of loop 

 
`filter()` is most convenient when you are not hand-rolling the
iterator. Because iterators are also iterable, you can iterate the
returned helper with a [`for...of`](../../statements/for...of) loop:

 
 
[js]


```js
for (const n of fibonacci().filter((x) => x % 2 === 0)) {
  console.log(n);
  if (n > 30) {
    break;
  }
}

// Logs:
// 2
// 8
// 34
```


This is equivalent to:

 
 
[js]


```js
for (const n of fibonacci()) {
  if (n % 2 !== 0) {
    continue;
  }
  console.log(n);
  if (n > 30) {
    break;
  }
}
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------
  [Iterator Helpers\
  [\#
  sec-iteratorprototype.filter]](https://tc39.es/proposal-iterator-helpers/#sec-iteratorprototype.filter)

  -----------------------------------------------------------------------------------------------------------------


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

`filter`

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

 
-   [Polyfill of `Iterator.prototype.filter` in
    `core-js`](https://github.com/zloirock/core-js#iterator-helpers)
-   [`Iterator`](../iterator)
-   [`Iterator.prototype.forEach()`](foreach)
-   [`Iterator.prototype.every()`](every)
-   [`Iterator.prototype.map()`](map)
-   [`Iterator.prototype.some()`](some)
-   [`Iterator.prototype.reduce()`](reduce)
-   [`Array.prototype.filter()`](../array/filter)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Iterator/filter>

