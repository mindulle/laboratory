TypedArray.prototype.some()
===========================

 
The `some()` method of [`TypedArray`](../typedarray) instances tests
whether at least one element in the typed array passes the test
implemented by the provided function. It returns true if, in the typed
array, it finds an element for which the provided function returns true;
otherwise it returns false. It doesn\'t modify the typed array. This
method has the same algorithm as
[`Array.prototype.some()`](../array/some).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
some(callbackFn)
some(callbackFn, thisArg)
```




 
### Parameters

 

[`callbackFn`](#callbackfn)

:   A function to execute for each element in the typed array. It should
    return a
    [truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy)
    value to indicate the element passes the test, and a
    [falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy)
    value otherwise. The function is called with the following
    arguments:

    [`element`](#element)

    :   The current element being processed in the typed array.

    [`index`](#index)

    :   The index of the current element being processed in the typed
        array.

    [`array`](#array)

    :   The typed array `some()` was called upon.

[`thisArg`](#thisarg) [Optional]

:   A value to use as `this` when executing `callbackFn`. See [iterative
    methods](../array#iterative_methods).



 
### Return value 

 
`false` unless `callbackFn` returns a
[truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy) value
for a typed array element, in which case `true` is immediately returned.



 
Description
-----------

 
See [`Array.prototype.some()`](../array/some) for more details. This
method is not generic and can only be called on typed array instances.



 
Examples
--------


 
### Testing size of all typed array elements 

 
The following example tests whether any element in the typed array is
bigger than 10.

 
 
[js]


```js
function isBiggerThan10(element, index, array) {
  return element > 10;
}
new Uint8Array([2, 5, 8, 1, 4]).some(isBiggerThan10); // false
new Uint8Array([12, 5, 8, 1, 4]).some(isBiggerThan10); // true
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\# sec-%typedarray%.prototype.some]](#)

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

`some`

45

12

37

32

10

45

37

32

10

5.0

45

1.0

4.0.0

 
See also 
--------

 
-   [Polyfill of `TypedArray.prototype.some` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-typed-arrays)
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [`TypedArray`](../typedarray)
-   [`TypedArray.prototype.every()`](every)
-   [`TypedArray.prototype.forEach()`](foreach)
-   [`TypedArray.prototype.find()`](find)
-   [`TypedArray.prototype.includes()`](includes)
-   [`Array.prototype.some()`](../array/some)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/some>

