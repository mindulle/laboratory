NaN
===

 
The `NaN` global property is a value representing Not-A-Number.


 
Try it 
------

 



 
Value
-----

 
The same number value as [`Number.NaN`](number/nan).

 
Property attributes of `NaN`




Writable

no

Enumerable

no

Configurable

no

 
Description
-----------

 
`NaN` is a property of the *global object*. In other words, it is a
variable in global scope.

In modern browsers, `NaN` is a non-configurable, non-writable property.
Even when this is not the case, avoid overriding it.

There are five different types of operations that return `NaN`:

-   Failed number conversion (e.g. explicit ones like
    `parseInt("blabla")`, `Number(undefined)`, or implicit ones like
    `Math.abs(undefined)`)
-   Math operation where the result is not a real number (e.g.
    `Math.sqrt(-1)`)
-   Indeterminate form (e.g. `0 * Infinity`, `1 ** Infinity`,
    `Infinity / Infinity`, `Infinity - Infinity`)
-   A method or expression whose operand is or gets coerced to `NaN`
    (e.g. `7 ** NaN`, `7 * "blabla"`) --- this means `NaN` is contagious
-   Other cases where an invalid value is to be represented as a number
    (e.g. an invalid [Date](date) `new Date("blabla").getTime()`,
    `"".charCodeAt(1)`)

`NaN` and its behaviors are not invented by JavaScript. Its semantics in
floating point arithmetic (including that `NaN !== NaN`) are specified
by [IEEE
754](https://en.wikipedia.org/wiki/Double_precision_floating-point_format).
`NaN`\'s behaviors include:

-   If `NaN` is involved in a mathematical operation (but not [bitwise
    operations](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#bitwise_shift_operators)),
    the result is usually also `NaN`. (See
    [counter-example](#silently_escaping_nan) below.)
-   When `NaN` is one of the operands of any relational comparison (`>`,
    `<`, `>=`, `<=`), the result is always `false`.
-   `NaN` compares unequal (via [`==`](../operators/equality),
    [`!=`](../operators/inequality),
    [`===`](../operators/strict_equality), and
    [`!==`](../operators/strict_inequality)) to any other value ---
    including to another `NaN` value.

`NaN` is also one of the
[falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy) values
in JavaScript.



 
Examples
--------


 
### Testing against NaN 

 
To tell if a value is `NaN`, use [`Number.isNaN()`](number/isnan) or
[`isNaN()`](isnan) to most clearly determine whether a value is `NaN`
--- or, since `NaN` is the only value that compares unequal to itself,
you can perform a self-comparison like `x !== x`.

 
 
[js]


```js
NaN === NaN; // false
Number.NaN === NaN; // false
isNaN(NaN); // true
isNaN(Number.NaN); // true
Number.isNaN(NaN); // true

function valueIsNaN(v) {
  return v !== v;
}
valueIsNaN(1); // false
valueIsNaN(NaN); // true
valueIsNaN(Number.NaN); // true
```


However, do note the difference between `isNaN()` and `Number.isNaN()`:
the former will return `true` if the value is currently `NaN`, or if it
is going to be `NaN` after it is coerced to a number, while the latter
will return `true` only if the value is currently `NaN`:

 
 
[js]


```js
isNaN("hello world"); // true
Number.isNaN("hello world"); // false
```


For the same reason, using a BigInt value will throw an error with
`isNaN()` and not with `Number.isNaN()`:

 
 
[js]


```js
isNaN(1n); // TypeError: Conversion from 'BigInt' to 'number' is not allowed.
Number.isNaN(1n); // false
```


Additionally, some array methods cannot find `NaN`, while others can.
Namely, the index-finding ones ([`indexOf()`](array/indexof),
[`lastIndexOf()`](array/lastindexof)) cannot find `NaN`, while the
value-finding ones ([`includes()`](array/includes)) can:

 
 
[js]


```js
const arr = [2, 4, NaN, 12];
arr.indexOf(NaN); // -1
arr.includes(NaN); // true

// Methods accepting a properly defined predicate can always find NaN
arr.findIndex((n) => Number.isNaN(n)); // 2
```


For more information about `NaN` and its comparison, see [Equality
comparison and
sameness](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Equality_comparisons_and_sameness).



 
### Observably distinct NaN values 

 
There\'s a motivation for `NaN` being unequal to itself. It\'s possible
to produce two floating point numbers with different binary
representations but are both `NaN`, because in [IEEE 754
encoding](https://en.wikipedia.org/wiki/NaN#Floating_point), any
floating point number with exponent `0x7ff` and a non-zero mantissa is
`NaN`. In JavaScript, you can do bit-level manipulation using [typed
arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays).

 
 
[js]


```js
const f2b = (x) => new Uint8Array(new Float64Array([x]).buffer);
const b2f = (x) => new Float64Array(x.buffer)[0];
// Get a byte representation of NaN
const n = f2b(NaN);
const m = f2b(NaN);
// Change the sign bit, which doesn't matter for NaN
n[7] += 2 ** 7;
// n[0] += 2**7; for big endian processors
const nan2 = b2f(n);
console.log(nan2); // NaN
console.log(Object.is(nan2, NaN)); // true
console.log(f2b(NaN)); // Uint8Array(8) [0, 0, 0, 0, 0, 0, 248, 127]
console.log(f2b(nan2)); // Uint8Array(8) [0, 0, 0, 0, 0, 0, 248, 255]
// Change the first bit, which is the least significant bit of the mantissa and doesn't matter for NaN
m[0] = 1;
// m[7] = 1; for big endian processors
const nan3 = b2f(m);
console.log(nan3); // NaN
console.log(Object.is(nan3, NaN)); // true
console.log(f2b(NaN)); // Uint8Array(8) [0, 0, 0, 0, 0, 0, 248, 127]
console.log(f2b(nan3)); // Uint8Array(8) [1, 0, 0, 0, 0, 0, 248, 127]
```




 
### Silently escaping NaN 

 
`NaN` propagates through mathematical operations, so it\'s usually
sufficient to test for `NaN` once at the end of calculation to detect
error conditions. The only case where `NaN` gets silently escaped is
when using [exponentiation](../operators/exponentiation) with an
exponent of `0`, which immediately returns `1` without testing the
base\'s value.

 
 
[js]


```js
NaN ** 0 === 1; // true
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-value-properties-of-the-global-object-nan]](https://tc39.es/ecma262/multipage/global-object.html#sec-value-properties-of-the-global-object-nan)

  -------------------------------------------------------------------------------------------------------------------------------------------------------------


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

`NaN`

1

12

1

4

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

 
-   [`Number.NaN`](number/nan)
-   [`Number.isNaN()`](number/isnan)
-   [`isNaN()`](isnan)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN>

