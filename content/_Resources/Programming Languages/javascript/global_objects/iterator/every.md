Iterator.prototype.every()
==========================

 
 
**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.


The `every()` method of [`Iterator`](../iterator) instances is similar
to [`Array.prototype.every()`](../array/every): it tests whether all
elements produced by the iterator pass the test implemented by the
provided function. It returns a boolean value.


 
Syntax
------

 
 
 
[js]


```js
every(callbackFn)
```




 
### Parameters

 

[`callbackFn`](#callbackfn)

:   A function to execute for each element produced by the iterator. It
    should return a
    [truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy)
    value to indicate the element passes the test, and a
    [falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy)
    value otherwise. The function is called with the following
    arguments:

    [`element`](#element)

    :   The current element being processed.

    [`index`](#index)

    :   The index of the current element being processed.



 
### Return value 

 
`true` if `callbackFn` returns a
[truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy) value
for every element. Otherwise, `false`.



 
Description
-----------

 
`every()` iterates the iterator and invokes the `callbackFn` function
once for each element. It returns `false` immediately if the callback
function returns a falsy value. Otherwise, it iterates until the end of
the iterator and returns `true`. If `every()` returns `false`, the
underlying iterator is closed by calling its `return()` method.

The main advantage of iterator helpers over array methods is their
ability to work with infinite iterators. With infinite iterators,
`every()` returns `false` as soon as the first falsy value is found. If
the `callbackFn` always returns a truthy value, the method never
returns.



 
Examples
--------


 
### Using every() 

 
 
 
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

const isEven = (x) => x % 2 === 0;
console.log(fibonacci().every(isEven)); // false

const isPositive = (x) => x > 0;
console.log(fibonacci().take(10).every(isPositive)); // true
console.log(fibonacci().every(isPositive)); // Never completes
```


Calling `every()` always closes the underlying iterator, even if the
method early-returns. The iterator is never left in a half-way state.

 
 
[js]


```js
const seq = fibonacci();
console.log(seq.every(isEven)); // false
console.log(seq.next()); // { value: undefined, done: true }
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------
  [Iterator Helpers\
  [\#
  sec-iteratorprototype.every]](https://tc39.es/proposal-iterator-helpers/#sec-iteratorprototype.every)

  ---------------------------------------------------------------------------------------------------------------


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

`every`

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

 
-   [Polyfill of `Iterator.prototype.every` in
    `core-js`](https://github.com/zloirock/core-js#iterator-helpers)
-   [`Iterator`](../iterator)
-   [`Iterator.prototype.find()`](find)
-   [`Iterator.prototype.some()`](some)
-   [`Array.prototype.every()`](../array/every)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Iterator/every>

