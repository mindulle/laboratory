RangeError: invalid array length
================================


The JavaScript exception \"Invalid array length\" occurs when specifying
an array length that is either negative, a floating number or exceeds
the maximum supported by the platform (i.e. when creating an
[`Array`](../global_objects/array) or
[`ArrayBuffer`](../global_objects/arraybuffer), or when setting the
[`length`](../global_objects/array/length) property).

The maximum allowed array length depends on the platform, browser and
browser version. For [`Array`](../global_objects/array) the maximum
length is 2^32^-1. For [`ArrayBuffer`](../global_objects/arraybuffer)
the maximum is 2^31^-1 (2GiB-1) on 32-bit systems. From Firefox version
89 the maximum value of [`ArrayBuffer`](../global_objects/arraybuffer)
is 2^33^ (8GiB) on 64-bit systems.

 
**Note:** `Array` and `ArrayBuffer` are independent data structures (the
implementation of one does not affect the other).




Message
-------


```text
RangeError: invalid array length (V8-based & Firefox)
RangeError: Array buffer allocation failed (V8-based)
RangeError: Array size is not a small enough positive integer. (Safari)
```




Error type 
----------


[`RangeError`](../global_objects/rangeerror)




What went wrong? 
----------------


An invalid array length might appear in these situations:

-   Creating an [`Array`](../global_objects/array) or
    [`ArrayBuffer`](../global_objects/arraybuffer) with a negative
    length, or setting a negative value for the
    [`length`](../global_objects/array/length) property.
-   Creating an [`Array`](../global_objects/array) or setting the
    [`length`](../global_objects/array/length) property greater than
    2^32^-1.
-   Creating an [`ArrayBuffer`](../global_objects/arraybuffer) that is
    bigger than 2^31^-1 (2GiB-1) on a 32-bit system, or 2^33^ (8GiB) on
    a 64-bit system.
-   Creating an [`Array`](../global_objects/array) or setting the
    [`length`](../global_objects/array/length) property to a
    floating-point number.
-   Before Firefox 89: Creating an
    [`ArrayBuffer`](../global_objects/arraybuffer) that is bigger than
    2^31^-1 (2GiB-1).

If you are creating an `Array`, using the constructor, you probably want
to use the literal notation instead, as the first argument is
interpreted as the length of the `Array`.

Otherwise, you might want to clamp the length before setting the length
property, or using it as argument of the constructor.




Examples
--------



### Invalid cases 




[js]


```js
new Array(Math.pow(2, 40));
new Array(-1);
new ArrayBuffer(Math.pow(2, 32)); // 32-bit system
new ArrayBuffer(-1);

const a = [];
a.length = a.length - 1; // set the length property to -1

const b = new Array(Math.pow(2, 32) - 1);
b.length = b.length + 1; // set the length property to 2^32
b.length = 2.5; // set the length property to a floating-point number

const c = new Array(2.5); // pass a floating-point number
```





### Valid cases 




[js]


```js
[Math.pow(2, 40)]; // [ 1099511627776 ]
[-1]; // [ -1 ]
new ArrayBuffer(Math.pow(2, 31) - 1);
new ArrayBuffer(Math.pow(2, 33)); // 64-bit systems after Firefox 89
new ArrayBuffer(0);

const a = [];
a.length = Math.max(0, a.length - 1);

const b = new Array(Math.pow(2, 32) - 1);
b.length = Math.min(0xffffffff, b.length + 1);
// 0xffffffff is the hexadecimal notation for 2^32 - 1
// which can also be written as (-1 >>> 0)

b.length = 3;

const c = new Array(3);
```





See also 
--------


-   [`Array`](../global_objects/array)
-   [`length`](../global_objects/array/length)
-   [`ArrayBuffer`](../global_objects/arraybuffer)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Invalid_array_length>

