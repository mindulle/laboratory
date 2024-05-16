RangeError: BigInt negative exponent
====================================


The JavaScript exception \"BigInt negative exponent\" occurs when a
[`BigInt`](../global_objects/bigint) is raised to the power of a
negative BigInt value.



Message
-------


```text
RangeError: Exponent must be positive (V8-based)
RangeError: BigInt negative exponent (Firefox)
RangeError: Negative exponent is not allowed (Safari)
```




Error type 
----------


[`RangeError`](../global_objects/rangeerror).




What went wrong? 
----------------


The exponent of an [exponentiation](../operators/exponentiation)
operation must be positive. Since negative exponents would take the
reciprocal of the base, the result will be between -1 and 1 in almost
all cases, which gets rounded to `0n`. To catch mistakes, negative
exponents are not allowed. Check if the exponent is non-negative before
doing exponentiation.




Examples
--------



### Using a negative BigInt as exponent 




[js]


```js
const a = 1n;
const b = -1n;
const c = a ** b;
// RangeError: BigInt negative exponent
```


Instead, check if the exponent is negative first, and either issue an
error with a better message, or fallback to a different value, like `0n`
or `undefined`.



[js]


```js
const a = 1n;
const b = -1n;
const quotient = b >= 0n ? a ** b : 0n;
```





See also 
--------


-   [`BigInt`](../global_objects/bigint)
-   [Exponentiation (`**`)](../operators/exponentiation)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/BigInt_negative_exponent>

