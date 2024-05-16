RangeError: BigInt division by zero
===================================


The JavaScript exception \"BigInt division by zero\" occurs when a
[`BigInt`](../global_objects/bigint) is divided by `0n`.



Message
-------


```text
RangeError: Division by zero (V8-based)
RangeError: BigInt division by zero (Firefox)
RangeError: 0 is an invalid divisor value. (Safari)
```




Error type 
----------


[`RangeError`](../global_objects/rangeerror).




What went wrong? 
----------------


The divisor of a [division](../operators/division) or
[remainder](../operators/remainder) operator is `0n`. In
[`Number`](../global_objects/number) arithmetic, this produces
[`Infinity`](../global_objects/infinity), but there\'s no \"infinity
value\" in BigInts, so an error is issued. Check if the divisor is `0n`
before doing the division.




Examples
--------



### Division by 0n 




[js]


```js
const a = 1n;
const b = 0n;
const quotient = a / b;
// RangeError: BigInt division by zero
```


Instead, check if the divisor is `0n` first, and either issue an error
with a better message, or fallback to a different value, like `Infinity`
or `undefined`.



[js]


```js
const a = 1n;
const b = 0n;
const quotient = b === 0n ? undefined : a / b;
```





See also 
--------


-   [`BigInt`](../global_objects/bigint)
-   [Division (`/`)](../operators/division)
-   [Remainder (`%`)](../operators/remainder)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/BigInt_division_by_zero>

