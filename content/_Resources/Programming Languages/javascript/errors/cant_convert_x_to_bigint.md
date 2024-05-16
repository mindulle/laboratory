TypeError: can\'t convert x to BigInt
=====================================


The JavaScript exception \"x can\'t be converted to BigInt\" occurs when
attempting to convert a [`Symbol`](../global_objects/symbol),
[`null`](../operators/null), or
[`undefined`](../global_objects/undefined) value to a
[`BigInt`](../global_objects/bigint), or if an operation expecting a
BigInt parameter receives a number.



Message
-------


```text
TypeError: Cannot convert null to a BigInt (V8-based)
TypeError: can't convert null to BigInt (Firefox)
TypeError: Invalid argument type in ToBigInt operation (Safari)
```




Error type 
----------


[`TypeError`](../global_objects/typeerror).




What went wrong? 
----------------


When using the [`BigInt()`](../global_objects/bigint/bigint) function to
convert a value to a BigInt, the value would first be converted to a
primitive. Then, if it\'s not one of BigInt, string, number, and
boolean, the error is thrown.

Some operations, like
[`BigInt.asIntN`](../global_objects/bigint/asintn), require the
parameter to be a BigInt. Passing in a number in this case will also
throw this error.




Examples
--------



### Using BigInt() on invalid values 




[js]


```js
const a = BigInt(null);
// TypeError: can't convert null to BigInt
const b = BigInt(undefined);
// TypeError: can't convert undefined to BigInt
const c = BigInt(Symbol("1"));
// TypeError: can't convert Symbol("1") to BigInt
```




[js]


```js
const a = BigInt(1);
const b = BigInt(true);
const c = BigInt("1");
const d = BigInt(Symbol("1").description);
```


 
**Note:** Simply coercing the value to a string or number using
[`String()`](../global_objects/string/string) or
[`Number()`](../global_objects/number/number) before passing it to
`BigInt()` is usually not sufficient to avoid all errors. If the string
is not a valid integer number string, a
[SyntaxError](invalid_bigint_syntax) is thrown; if the number is not an
integer (most notably, [`NaN`](../global_objects/nan)), a
[RangeError](cant_be_converted_to_bigint_because_it_isnt_an_integer) is
thrown. If the range of input is unknown, properly validate it before
using `BigInt()`.





### Passing a number to a function expecting a BigInt 




[js]


```js
const a = BigInt.asIntN(4, 8);
// TypeError: can't convert 8 to BigInt
const b = new BigInt64Array(3).fill(3);
// TypeError: can't convert 3 to BigInt
```




[js]


```js
const a = BigInt.asIntN(4, 8n);
const b = new BigInt64Array(3).fill(3n);
```





See also 
--------


-   [`BigInt()` constructor](../global_objects/bigint/bigint)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Cant_convert_x_to_BigInt>

