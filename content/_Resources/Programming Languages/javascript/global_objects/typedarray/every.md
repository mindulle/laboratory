TypedArray.prototype.every()
============================

 
The `every()` method of [`TypedArray`](../typedarray) instances tests
whether all elements in the typed array pass the test implemented by the
provided function. It returns a Boolean value. This method has the same
algorithm as [`Array.prototype.every()`](../array/every).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
every(callbackFn)
every(callbackFn, thisArg)
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

    :   The typed array `every()` was called upon.

[`thisArg`](#thisarg) [Optional]

:   A value to use as `this` when executing `callbackFn`. See [iterative
    methods](../array#iterative_methods).



 
### Return value 

 
`true` unless `callbackFn` returns a
[falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy) value
for a typed array element, in which case `false` is immediately
returned.



 
Description
-----------

 
See [`Array.prototype.every()`](../array/every) for more details. This
method is not generic and can only be called on typed array instances.



 
Examples
--------


 
### Testing size of all typed array elements 

 
The following example tests whether all elements in the typed array are
10 or bigger.

 
 
[js]


```js
function isBigEnough(element, index, array) {
  return element >= 10;
}
new Uint8Array([12, 5, 8, 130, 44]).every(isBigEnough); // false
new Uint8Array([12, 54, 18, 130, 44]).every(isBigEnough); // true
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\# sec-%typedarray%.prototype.every]](#)

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

`every`

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

 
-   [Polyfill of `TypedArray.prototype.every` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-typed-arrays)
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [`TypedArray`](../typedarray)
-   [`TypedArray.prototype.forEach()`](foreach)
-   [`TypedArray.prototype.some()`](some)
-   [`TypedArray.prototype.find()`](find)
-   [`Array.prototype.every()`](../array/every)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/every>

