TypeError: can\'t convert BigInt to number
==========================================


The JavaScript exception \"can\'t convert BigInt to number\" occurs when
an arithmetic operation involves a mix of
[`BigInt`](../global_objects/bigint) and
[`Number`](../global_objects/number) values.



Message
-------


```text
TypeError: Cannot mix BigInt and other types, use explicit conversions (V8-based)
TypeError: BigInts have no unsigned right shift, use >> instead (V8-based)
TypeError: can't convert BigInt to number (Firefox)
TypeError: Invalid mix of BigInt and other type in addition/multiplication/…. (Safari)
TypeError: BigInt does not support >>> operator (Safari)
```




Error type 
----------


[`TypeError`](../global_objects/typeerror).




What went wrong? 
----------------


The two sides of an arithmetic operator must both be BigInts or both
not. If an operation involves a mix of BigInts and numbers, it\'s
ambiguous whether the result should be a BigInt or number, since there
may be loss of precision in both cases.

The error can also happen if the [unsigned right shift operator
(`>>>`)](../operators/unsigned_right_shift) is used between two BigInts.
In Firefox, the message is the same: \"can\'t convert BigInt to
number\".




Examples
--------



### Mixing numbers and BigInts in operations 




[js]


```js
const sum = 1n + 1;
// TypeError: can't convert BigInt to number
```


Instead, explicitly coerce one side to a BigInt or number.



[js]


```js
const sum = 1n + BigInt(1);
const sum2 = Number(1n) + 1;
```





### Using unsigned right shift on BigInts 




[js]


```js
const a = 4n >>> 2n;
// TypeError: can't convert BigInt to number
```


Use normal right shift instead.



[js]


```js
const a = 4n >> 2n;
```





See also 
--------


-   [`BigInt`](../global_objects/bigint)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Cant_convert_BigInt_to_number>

