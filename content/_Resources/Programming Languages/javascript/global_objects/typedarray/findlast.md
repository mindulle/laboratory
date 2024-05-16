TypedArray.prototype.findLast()
===============================

 
The `findLast()` method of [`TypedArray`](../typedarray) instances
iterates the typed array in reverse order and returns the value of the
first element that satisfies the provided testing function. If no
elements satisfy the testing function, [`undefined`](../undefined) is
returned. This method has the same algorithm as
[`Array.prototype.findLast()`](../array/findlast).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
findLast(callbackFn)
findLast(callbackFn, thisArg)
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

    :   The typed array `findLast()` was called upon.

[`thisArg`](#thisarg) [Optional]

:   A value to use as `this` when executing `callbackFn`. See [iterative
    methods](../array#iterative_methods).



 
### Return value 

 
The last (highest-index) element in the typed array that satisfies the
provided testing function; [`undefined`](../undefined) if no matching
element is found.



 
Description
-----------

 
See [`Array.prototype.findLast()`](../array/findlast) for more details.
This method is not generic and can only be called on typed array
instances.



 
Examples
--------


 
### Find the last prime number in a typed array 

 
The following example returns the value of the last element in the typed
array that is a prime number, or [`undefined`](../undefined) if there is
no prime number.

 
 
[js]


```js
function isPrime(element) {
  if (element % 2 === 0 || element < 2) {
    return false;
  }
  for (let factor = 3; factor <= Math.sqrt(element); factor += 2) {
    if (element % factor === 0) {
      return false;
    }
  }
  return true;
}

let uint8 = new Uint8Array([4, 6, 8, 12]);
console.log(uint8.findLast(isPrime)); // undefined (no primes in array)
uint8 = new Uint8Array([4, 5, 7, 8, 9, 11, 12]);
console.log(uint8.findLast(isPrime)); // 11
```




 
### All elements are visited and may be modified by the callback 

 
The following examples show that all elements *are* visited, and that
the value passed to the callback is their value when visited:

 
 
[js]


```js
// Declare array with no elements at indexes 2, 3, and 4
// The missing elements will be initialized to zero.
const uint8 = new Uint8Array([0, 1, , , , 5, 6]);

// Iterate through the elements in reverse order.
// Note that all elements are visited.
uint8.findLast((value, index) => {
  console.log(`Visited index ${index} with value ${value}`);
});

// Shows all indexes, including deleted
uint8.findLast((value, index) => {
  // Modify element 3 on first iteration
  if (index === 6) {
    console.log("Set uint8[3] to 44");
    uint8[3] = 44;
  }
  // Element 3 is still visited but will have a new value.
  console.log(`Visited index ${index} with value ${value}`);
});
// Visited index 6 with value 6
// Visited index 5 with value 5
// Visited index 4 with value 0
// Visited index 3 with value 0
// Visited index 2 with value 0
// Visited index 1 with value 1
// Visited index 0 with value 0
// Set uint8[3] to 44
// Visited index 6 with value 6
// Visited index 5 with value 5
// Visited index 4 with value 0
// Visited index 3 with value 44
// Visited index 2 with value 0
// Visited index 1 with value 1
// Visited index 0 with value 0
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\# sec-%typedarray%.prototype.findlast]](#)

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

`findLast`

97

97

104

83

15.4

97

104

68

15.4

18.0

97

1.16

No

 
See also 
--------

 
-   [Polyfill of `TypedArray.prototype.findLast` in
    `core-js`](https://github.com/zloirock/core-js#array-find-from-last)
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [`TypedArray`](../typedarray)
-   [`TypedArray.prototype.find()`](find)
-   [`TypedArray.prototype.findIndex()`](findindex)
-   [`TypedArray.prototype.findLastIndex()`](findlastindex)
-   [`TypedArray.prototype.includes()`](includes)
-   [`TypedArray.prototype.filter()`](filter)
-   [`TypedArray.prototype.every()`](every)
-   [`TypedArray.prototype.some()`](some)
-   [`Array.prototype.findLast()`](../array/findlast)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/findLast>

