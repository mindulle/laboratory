Number.POSITIVE\_INFINITY
=========================

 
The `Number.POSITIVE_INFINITY` static data property represents the
positive Infinity value.


 
Try it 
------

 



 
Value
-----

 
The same as the value of the global [`Infinity`](../infinity) property.

 
Property attributes of `Number.POSITIVE_INFINITY`




Writable

no

Enumerable

no

Configurable

no

 
Description
-----------

 
The `Number.POSITIVE_INFINITY` value behaves slightly differently than
mathematical infinity:

-   Any positive value, including `POSITIVE_INFINITY`, multiplied by
    `POSITIVE_INFINITY` is `POSITIVE_INFINITY`.
-   Any negative value, including
    [`NEGATIVE_INFINITY`](negative_infinity), multiplied by
    `POSITIVE_INFINITY` is [`NEGATIVE_INFINITY`](negative_infinity).
-   Any positive number divided by `POSITIVE_INFINITY` is [positive
    zero](https://en.wikipedia.org/wiki/Signed_zero) (as defined in
    [IEEE 754](https://en.wikipedia.org/wiki/IEEE_754)).
-   Any negative number divided by `POSITIVE_INFINITY` is [negative
    zero](https://en.wikipedia.org/wiki/Signed_zero) (as defined in
    [IEEE 754](https://en.wikipedia.org/wiki/IEEE_754).
-   Zero multiplied by `POSITIVE_INFINITY` is [`NaN`](../nan).
-   [`NaN`](../nan) multiplied by `POSITIVE_INFINITY` is
    [`NaN`](../nan).
-   `POSITIVE_INFINITY`, divided by any negative value except
    [`NEGATIVE_INFINITY`](negative_infinity), is
    [`NEGATIVE_INFINITY`](negative_infinity).
-   `POSITIVE_INFINITY`, divided by any positive value except
    `POSITIVE_INFINITY`, is `POSITIVE_INFINITY`.
-   `POSITIVE_INFINITY`, divided by either
    [`NEGATIVE_INFINITY`](negative_infinity) or `POSITIVE_INFINITY`, is
    [`NaN`](../nan).
-   `Number.POSITIVE_INFINITY > x` is true for any number *x* that
    isn\'t `POSITIVE_INFINITY`.

You might use the `Number.POSITIVE_INFINITY` property to indicate an
error condition that returns a finite number in case of success. Note,
however, that [`NaN`](../nan) would be more appropriate in such a case.

Because `POSITIVE_INFINITY` is a static property of
[`Number`](../number), you always use it as `Number.POSITIVE_INFINITY`,
rather than as a property of a number value.



 
Examples
--------


 
### Using POSITIVE\_INFINITY 

 
In the following example, the variable `bigNumber` is assigned a value
that is larger than the maximum value. When the
[`if`](../../statements/if...else) statement executes, `bigNumber` has
the value `Infinity`, so `bigNumber` is set to a more manageable value
before continuing.

 
 
[js]


```js
let bigNumber = Number.MAX_VALUE * 2;

if (bigNumber === Number.POSITIVE_INFINITY) {
  bigNumber = returnFinite();
}
```




Specifications
--------------

 
  --------------------------------------------------------------------------------------------------------------------------------
  Specification
  --------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-number.positive\_infinity]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-number.positive_infinity)

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

`POSITIVE_INFINITY`

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

 
-   [`Number.NEGATIVE_INFINITY`](negative_infinity)
-   [`Number.isFinite()`](isfinite)
-   [`Infinity`](../infinity)
-   [`isFinite()`](../isfinite)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/POSITIVE_INFINITY>

