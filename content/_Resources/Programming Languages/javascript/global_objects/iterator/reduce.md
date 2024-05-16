Iterator.prototype.reduce()
===========================

 
 
**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.


The `reduce()` method of [`Iterator`](../iterator) instances is similar
to [`Array.prototype.reduce`](../array/reduce): it executes a
user-supplied \"reducer\" callback function on each element produced by
the iterator, passing in the return value from the calculation on the
preceding element. The final result of running the reducer across all
elements is a single value.


 
Syntax
------

 
 
 
[js]


```js
reduce(callbackFn)
reduce(callbackFn, initialValue)
```




 
### Parameters

 

[`callbackFn`](#callbackfn)

:   A function to execute for each element produced by the iterator. Its
    return value becomes the value of the `accumulator` parameter on the
    next invocation of `callbackFn`. For the last invocation, the return
    value becomes the return value of `reduce()`. The function is called
    with the following arguments:

    [`accumulator`](#accumulator)

    :   The value resulting from the previous call to `callbackFn`. On
        the first call, its value is `initialValue` if the latter is
        specified; otherwise its value is the first element of the
        iterator.

    [`currentValue`](#currentvalue)

    :   The value of the current element. On the first call, its value
        is the first element of the iterator if `initialValue` is
        specified; otherwise its value is the second element.

    [`currentIndex`](#currentindex)

    :   The index position of `currentValue`. On the first call, its
        value is `0` if `initialValue` is specified, otherwise `1`.

[`initialValue`](#initialvalue) [Optional]

:   A value to which `accumulator` is initialized the first time the
    callback is called. If `initialValue` is specified, `callbackFn`
    starts executing with the first element as `currentValue`. If
    `initialValue` is *not* specified, `accumulator` is initialized to
    the first element, and `callbackFn` starts executing with the second
    element as `currentValue`. In this case, if the iterator is empty
    (so that there\'s no first value to return as `accumulator`), an
    error is thrown.



 
### Return value 

 
The value that results from running the \"reducer\" callback function to
completion over the entire iterator.



 
### Exceptions

 

[`TypeError`](../typeerror)

:   Thrown if the iterator contains no elements and `initialValue` is
    not provided.



 
Description
-----------

 
See [`Array.prototype.reduce()`](../array/reduce) for details about how
`reduce()` works. Unlike most other iterator helper methods, it does not
work well with infinite iterators, because it is not lazy.



 
Examples
--------


 
### Using reduce() 

 
The following example creates an iterator that yields terms in the
Fibonacci sequence, and then sums the first ten terms:

 
 
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

console.log(
  fibonacci()
    .take(10)
    .reduce((a, b) => a + b),
); // 143
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------------
  [Iterator Helpers\
  [\#
  sec-iteratorprototype.reduce]](https://tc39.es/proposal-iterator-helpers/#sec-iteratorprototype.reduce)

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

`reduce`

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

 
-   [Polyfill of `Iterator.prototype.reduce` in
    `core-js`](https://github.com/zloirock/core-js#iterator-helpers)
-   [`Iterator`](../iterator)
-   [`Iterator.prototype.map()`](map)
-   [`Iterator.prototype.flatMap()`](flatmap)
-   [`Array.prototype.reduce()`](../array/reduce)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Iterator/reduce>

