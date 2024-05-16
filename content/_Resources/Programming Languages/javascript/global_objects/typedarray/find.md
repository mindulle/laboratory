TypedArray.prototype.find()
===========================

 
The `find()` method of [`TypedArray`](../typedarray) instances returns
the first element in the provided typed array that satisfies the
provided testing function. If no values satisfy the testing function,
[`undefined`](../undefined) is returned. This method has the same
algorithm as [`Array.prototype.find()`](../array/find).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
find(callbackFn)
find(callbackFn, thisArg)
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

    :   The typed array `find()` was called upon.

[`thisArg`](#thisarg) [Optional]

:   A value to use as `this` when executing `callbackFn`. See [iterative
    methods](../array#iterative_methods).



 
### Return value 

 
The first element in the typed array that satisfies the provided testing
function. Otherwise, [`undefined`](../undefined) is returned.



 
Description
-----------

 
See [`Array.prototype.find()`](../array/find) for more details. This
method is not generic and can only be called on typed array instances.



 
Examples
--------


 
### Find a prime number in a typed array 

 
The following example finds an element in the typed array that is a
prime number (or returns [`undefined`](../undefined) if there is no
prime number).

 
 
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

const uint8 = new Uint8Array([4, 5, 8, 12]);
console.log(uint8.find(isPrime)); // 5
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\# sec-%typedarray%.prototype.find]](#)

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

`find`

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

 
-   [Polyfill of `TypedArray.prototype.find` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-typed-arrays)
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [`TypedArray`](../typedarray)
-   [`TypedArray.prototype.findIndex()`](findindex)
-   [`TypedArray.prototype.findLast()`](findlast)
-   [`TypedArray.prototype.findLastIndex()`](findlastindex)
-   [`TypedArray.prototype.includes()`](includes)
-   [`TypedArray.prototype.filter()`](filter)
-   [`TypedArray.prototype.every()`](every)
-   [`TypedArray.prototype.some()`](some)
-   [`Array.prototype.find()`](../array/find)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/find>

