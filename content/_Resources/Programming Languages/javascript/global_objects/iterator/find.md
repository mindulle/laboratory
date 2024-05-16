Iterator.prototype.find()
=========================

 
 
**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.


The `find()` method of [`Iterator`](../iterator) instances is similar to
[`Array.prototype.find()`](../array/find): it returns the first element
produced by the iterator that satisfies the provided testing function.
If no values satisfy the testing function, [`undefined`](../undefined)
is returned.


 
Syntax
------

 
 
 
[js]


```js
find(callbackFn)
```




 
### Parameters

 

[`callbackFn`](#callbackfn)

:   A function to execute for each element produced by the iterator. It
    should return a
    [truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy)
    value to indicate a matching element has been found, and a
    [falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy)
    value otherwise. The function is called with the following
    arguments:

    [`element`](#element)

    :   The current element being processed.

    [`index`](#index)

    :   The index of the current element being processed.



 
### Return value 

 
The first element produced by the iterator that satisfies the provided
testing function. Otherwise, [`undefined`](../undefined) is returned.



 
Description
-----------

 
`find()` iterates the iterator and invokes the `callbackFn` function
once for each element. It returns the element immediately if the
callback function returns a truthy value. Otherwise, it iterates until
the end of the iterator and returns `undefined`. If `find()` returns an
element, the underlying iterator is closed by calling its `return()`
method.

The main advantage of iterator helpers over array methods is their
ability to work with infinite iterators. With infinite iterators,
`find()` returns the first satisfying element as soon as it is found. If
the `callbackFn` always returns a falsy value, the method never returns.



 
Examples
--------


 
### Using find() 

 
 
 
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
console.log(fibonacci().find(isEven)); // 2

const isNegative = (x) => x < 0;
console.log(fibonacci().take(10).find(isNegative)); // undefined
console.log(fibonacci().find(isNegative)); // Never completes
```


Calling `find()` always closes the underlying iterator, even if the
method early-returns. The iterator is never left in a half-way state.

 
 
[js]


```js
const seq = fibonacci();
console.log(seq.find(isEven)); // 2
console.log(seq.next()); // { value: undefined, done: true }
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------
  [Iterator Helpers\
  [\#
  sec-iteratorprototype.find]](https://tc39.es/proposal-iterator-helpers/#sec-iteratorprototype.find)

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

`find`

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

 
-   [Polyfill of `Iterator.prototype.find` in
    `core-js`](https://github.com/zloirock/core-js#iterator-helpers)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Iterator/find>

