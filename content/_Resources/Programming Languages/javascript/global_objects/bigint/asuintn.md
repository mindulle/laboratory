BigInt.asUintN()
================

Baseline [Widely available]
--------------------------------------


This feature is well established and works across many devices and
browser versions. It's been available across browsers since September
2020.

-   [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-evolution-on-mdn/)
-   [See full compatibility](#browser_compatibility)
-   [Report
    feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FJavaScript%2FReference%2FGlobal_Objects%2FBigInt%2FasUintN&level=high)



The `BigInt.asUintN()` static method truncates a `BigInt` value to the
given number of least significant bits and returns that value as an
unsigned integer.



Try it 
------






Syntax
------




[js]


```js
BigInt.asUintN(bits, bigint)
```





### Parameters



[`bits`](#bits)

:   The amount of bits available for the returned BigInt. Should be an
    integer between 0 and 2^53^ - 1, inclusive.

[`bigint`](#bigint)

:   The BigInt value to truncate to fit into the supplied bits.




### Return value 


The value of `bigint` modulo 2\^`bits`, as an unsigned integer.




### Exceptions



[`RangeError`](../rangeerror)

:   Thrown if `bits` is negative or greater than 2^53^ - 1.




Description
-----------


The `BigInt.asUintN` method truncates a `BigInt` value to the given
number of bits, and interprets the result as an unsigned integer.
Unsigned integers have no sign bits and are always non-negative. For
example, for `BigInt.asUintN(4, 25n)`, the value `25n` is truncated to
`9n`:

```text
25n = 00011001 (base 2)
         ^==== Use only the four remaining bits
===>      1001 (base 2) = 9n
```

 
**Note:** `BigInt` values are always encoded as two\'s complement in
binary.


Unlike similar language APIs such as
[`Number.prototype.toExponential()`](../number/toexponential), `asUintN`
is a static property of [`BigInt`](../bigint), so you always use it as
`BigInt.asUintN()`, rather than as a method of a BigInt value. Exposing
`asUintN()` as a \"standard library function\" allows [interop with
asm.js](https://github.com/tc39/proposal-bigint/blob/master/ADVANCED.md#dont-break-asmjs).




Examples
--------



### Staying in 64-bit ranges 


The `BigInt.asUintN()` method can be useful to stay in the range of
64-bit arithmetic.



[js]


```js
const max = 2n ** 64n - 1n;

BigInt.asUintN(64, max); // 18446744073709551615n

BigInt.asUintN(64, max + 1n); // 0n
// zero because of overflow: the lowest 64 bits are all zeros
```




Specifications
--------------


  -----------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-bigint.asuintn]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-bigint.asuintn)

  -----------------------------------------------------------------------------------------------------------


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

`asUintN`

67

79

68

54

14

67

68

48

14

9.0

67

1.0

10.4.0


See also 
--------


-   [`BigInt`](../bigint)
-   [`BigInt.asIntN()`](asintn)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/BigInt/asUintN>

