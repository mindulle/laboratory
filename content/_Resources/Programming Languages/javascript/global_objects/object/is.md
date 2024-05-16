Object.is()
===========

 
The `Object.is()` static method determines whether two values are [the
same
value](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Equality_comparisons_and_sameness#same-value_equality_using_object.is).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Object.is(value1, value2)
```




 
### Parameters

 

[`value1`](#value1)

:   The first value to compare.

[`value2`](#value2)

:   The second value to compare.



 
### Return value 

 
A boolean indicating whether or not the two arguments are the same
value.



 
Description
-----------

 
`Object.is()` determines whether two values are [the same
value](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Equality_comparisons_and_sameness#same-value_equality_using_object.is).
Two values are the same if one of the following holds:

-   both [`undefined`](../undefined)
-   both [`null`](../../operators/null)
-   both `true` or both `false`
-   both strings of the same length with the same characters in the same
    order
-   both the same object (meaning both values reference the same object
    in memory)
-   both [BigInts](../bigint) with the same numeric value
-   both [symbols](../symbol) that reference the same symbol value
-   both numbers and
    -   both `+0`
    -   both `-0`
    -   both [`NaN`](../nan)
    -   or both non-zero, not [`NaN`](../nan), and have the same value

`Object.is()` is not equivalent to the [`==`](../../operators/equality)
operator. The `==` operator applies various coercions to both sides (if
they are not the same type) before testing for equality (resulting in
such behavior as `"" == false` being `true`), but `Object.is()` doesn\'t
coerce either value.

`Object.is()` is also *not* equivalent to the
[`===`](../../operators/strict_equality) operator. The only difference
between `Object.is()` and `===` is in their treatment of signed zeros
and `NaN` values. The `===` operator (and the `==` operator) treats the
number values `-0` and `+0` as equal, but treats [`NaN`](../nan) as not
equal to each other.



 
Examples
--------


 
### Using Object.is() 

 
 
 
[js]


```js
// Case 1: Evaluation result is the same as using ===
Object.is(25, 25); // true
Object.is("foo", "foo"); // true
Object.is("foo", "bar"); // false
Object.is(null, null); // true
Object.is(undefined, undefined); // true
Object.is(window, window); // true
Object.is([], []); // false
const foo = { a: 1 };
const bar = { a: 1 };
const sameFoo = foo;
Object.is(foo, foo); // true
Object.is(foo, bar); // false
Object.is(foo, sameFoo); // true

// Case 2: Signed zero
Object.is(0, -0); // false
Object.is(+0, -0); // false
Object.is(-0, -0); // true

// Case 3: NaN
Object.is(NaN, 0 / 0); // true
Object.is(NaN, Number.NaN); // true
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-object.is]](https://tc39.es/ecma262/multipage/fundamental-objects.html#sec-object.is)

  ---------------------------------------------------------------------------------------------------


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

`is`

19

12

22

15

9

25

22

14

9

1.5

4.4

1.0

0.10.0

 
See also 
--------

 
-   [Polyfill of `Object.is` in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-object)
-   [Equality comparisons and
    sameness](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Equality_comparisons_and_sameness)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/is>

