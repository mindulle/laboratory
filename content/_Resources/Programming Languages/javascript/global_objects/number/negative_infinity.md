Number.NEGATIVE\_INFINITY
=========================

 
The `Number.NEGATIVE_INFINITY` static data property represents the
negative Infinity value.


 
Try it 
------

 



 
Value
-----

 
The same as the negative value of the global [`Infinity`](../infinity)
property.

 
Property attributes of `Number.NEGATIVE_INFINITY`




Writable

no

Enumerable

no

Configurable

no

 
Description
-----------

 
The `Number.NEGATIVE_INFINITY` value behaves slightly differently than
mathematical infinity:

-   Any positive value, including
    [`POSITIVE_INFINITY`](positive_infinity), multiplied by
    `NEGATIVE_INFINITY` is `NEGATIVE_INFINITY`.
-   Any negative value, including `NEGATIVE_INFINITY`, multiplied by
    `NEGATIVE_INFINITY` is [`POSITIVE_INFINITY`](positive_infinity).
-   Any positive value divided by `NEGATIVE_INFINITY` is [negative
    zero](https://en.wikipedia.org/wiki/Signed_zero) (as defined in
    [IEEE 754](https://en.wikipedia.org/wiki/IEEE_754)).
-   Any negative value divided by `NEGATIVE_INFINITY` is [positive
    zero](https://en.wikipedia.org/wiki/Signed_zero) (as defined in
    [IEEE 754](https://en.wikipedia.org/wiki/IEEE_754)).
-   Zero multiplied by `NEGATIVE_INFINITY` is [`NaN`](../nan).
-   [`NaN`](../nan) multiplied by `NEGATIVE_INFINITY` is
    [`NaN`](../nan).
-   `NEGATIVE_INFINITY`, divided by any negative value except
    `NEGATIVE_INFINITY`, is [`POSITIVE_INFINITY`](positive_infinity).
-   `NEGATIVE_INFINITY`, divided by any positive value except
    [`POSITIVE_INFINITY`](positive_infinity), is `NEGATIVE_INFINITY`.
-   `NEGATIVE_INFINITY`, divided by either `NEGATIVE_INFINITY` or
    [`POSITIVE_INFINITY`](positive_infinity), is [`NaN`](../nan).
-   `x > Number.NEGATIVE_INFINITY` is true for any number *x* that
    isn\'t `NEGATIVE_INFINITY`.

You might use the `Number.NEGATIVE_INFINITY` property to indicate an
error condition that returns a finite number in case of success. Note,
however, that [`NaN`](../nan) would be more appropriate in such a case.

Because `NEGATIVE_INFINITY` is a static property of
[`Number`](../number), you always use it as `Number.NEGATIVE_INFINITY`,
rather than as a property of a number value.



 
Examples
--------


 
### Using NEGATIVE\_INFINITY 

 
In the following example, the variable `smallNumber` is assigned a value
that is smaller than the minimum value. When the
[`if`](../../statements/if...else) statement executes, `smallNumber` has
the value `-Infinity`, so `smallNumber` is set to a more manageable
value before continuing.

 
 
[js]


```js
let smallNumber = -Number.MAX_VALUE * 2;

if (smallNumber === Number.NEGATIVE_INFINITY) {
  smallNumber = returnFinite();
}
```




Specifications
--------------

 
  --------------------------------------------------------------------------------------------------------------------------------
  Specification
  --------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-number.negative\_infinity]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-number.negative_infinity)

  --------------------------------------------------------------------------------------------------------------------------------


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

`NEGATIVE_INFINITY`

1

12

1

3

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

 
See also 
--------

 
-   [`Number.POSITIVE_INFINITY`](positive_infinity)
-   [`Number.isFinite()`](isfinite)
-   [`Infinity`](../infinity)
-   [`isFinite()`](../isfinite)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/NEGATIVE_INFINITY>

