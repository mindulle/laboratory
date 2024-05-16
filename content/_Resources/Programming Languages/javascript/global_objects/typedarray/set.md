TypedArray.prototype.set()
==========================

 
The `set()` method of [`TypedArray`](../typedarray) instances stores
multiple values in the typed array, reading input values from a
specified array.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
set(array)
set(array, targetOffset)

set(typedarray)
set(typedarray, targetOffset)
```




 
### Parameters

 

[`array`](#array)

:   The array from which to copy values. All values from the source
    array are copied into the target array, unless the length of the
    source array plus the target offset exceeds the length of the target
    array, in which case an exception is thrown.

[`typedarray`](#typedarray)

:   If the source array is a typed array, the two arrays may share the
    same underlying [`ArrayBuffer`](../arraybuffer); the JavaScript
    engine will intelligently **copy** the source range of the buffer to
    the destination range.

[`targetOffset`](#targetoffset) [Optional]

:   The offset into the target array at which to begin writing values
    from the source array. If this value is omitted, 0 is assumed (that
    is, the source array will overwrite values in the target array
    starting at index 0).



 
### Return value 

 
None ([`undefined`](../undefined)).



 
### Exceptions

 

[`RangeError`](../rangeerror)

:   Thrown in one of the following cases:

    -   An element will be stored beyond the end of the typed array,
        either because `targetOffset` is too large or because `array` or
        `typedarray` is too large.
    -   `targetOffset` is negative.



 
Examples
--------


 
### Using set() 

 
 
 
[js]


```js
const buffer = new ArrayBuffer(8);
const uint8 = new Uint8Array(buffer);

uint8.set([1, 2, 3], 3);

console.log(uint8); // Uint8Array [ 0, 0, 0, 1, 2, 3, 0, 0 ]
```




Specifications
--------------

 
  -----------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\# sec-%typedarray%.prototype.set]](#)

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

`set`

7

12

4

11.6

5.1

18

4

12

4.2

1.0

4

1.0

0.10.0

 
See also 
--------

 
-   [Polyfill of `TypedArray.prototype.set` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-typed-arrays)
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [`TypedArray`](../typedarray)
-   [`ArrayBuffer`](../arraybuffer)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/set>

