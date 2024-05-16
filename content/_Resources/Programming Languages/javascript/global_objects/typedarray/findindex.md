TypedArray.prototype.findIndex()
================================

 
The `findIndex()` method of [`TypedArray`](../typedarray) instances
returns the index of the first element in a typed array that satisfies
the provided testing function. If no elements satisfy the testing
function, -1 is returned. This method has the same algorithm as
[`Array.prototype.findIndex()`](../array/findindex).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
findIndex(callbackFn)
findIndex(callbackFn, thisArg)
```




 
### Parameters

 

[`callbackFn`](#callbackfn)

:   A function to execute for each element in the typed array. It should
    return a
    [truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy)
    value to indicate a matching element has been found, and a
    [falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy)
    value otherwise. The function is called with the following
    arguments:

    [`element`](#element)

    :   The current element being processed in the typed array.

    [`index`](#index)

    :   The index of the current element being processed in the typed
        array.

    [`array`](#array)

    :   The typed array `findIndex()` was called upon.

[`thisArg`](#thisarg) [Optional]

:   A value to use as `this` when executing `callbackFn`. See [iterative
    methods](../array#iterative_methods).



 
### Return value 

 
The index of the first element in the typed array that passes the test.
Otherwise, `-1`.



 
Description
-----------

 
See [`Array.prototype.findIndex()`](../array/findindex) for more
details. This method is not generic and can only be called on typed
array instances.



 
Examples
--------


 
### Find the index of a prime number in a typed array 

 
The following example finds the index of an element in the typed array
that is a prime number (or returns `-1` if there is no prime number).

 
 
[js]


```js
function isPrime(element, index, array) {
  let start = 2;
  while (start <= Math.sqrt(element)) {
    if (element % start++ < 1) {
      return false;
    }
  }
  return element > 1;
}

const uint8 = new Uint8Array([4, 6, 8, 12]);
const uint16 = new Uint16Array([4, 6, 7, 12]);

console.log(uint8.findIndex(isPrime)); // -1, not found
console.log(uint16.findIndex(isPrime)); // 2
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\# sec-%typedarray%.prototype.findindex]](#)

  -----------------------------------------------------------------------


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

`findIndex`

45

12

37

32

9.1

45

37

32

9.3

5.0

45

1.0

4.0.0

 
See also 
--------

 
-   [Polyfill of `TypedArray.prototype.findIndex` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-typed-arrays)
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [`TypedArray`](../typedarray)
-   [`TypedArray.prototype.find()`](find)
-   [`TypedArray.prototype.findLast()`](findlast)
-   [`TypedArray.prototype.findLastIndex()`](findlastindex)
-   [`TypedArray.prototype.indexOf()`](indexof)
-   [`TypedArray.prototype.lastIndexOf()`](lastindexof)
-   [`Array.prototype.findIndex()`](../array/findindex)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/findIndex>

