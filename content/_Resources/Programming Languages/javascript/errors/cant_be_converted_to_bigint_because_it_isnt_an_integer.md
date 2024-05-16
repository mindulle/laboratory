RangeError: x can\'t be converted to BigInt because it isn\'t an integer
========================================================================


The JavaScript exception \"x can\'t be converted to BigInt because it
isn\'t an integer\" occurs when the
[`BigInt()`](../global_objects/bigint/bigint) function is used on a
number that isn\'t an integer.



Message
-------


```text
RangeError: The number 1.5 cannot be converted to a BigInt because it is not an integer (V8-based & Firefox)
RangeError: Not an integer (Safari)
```




Error type 
----------


[`RangeError`](../global_objects/rangeerror).




What went wrong? 
----------------


When using the [`BigInt()`](../global_objects/bigint/bigint) function to
convert a number to a BigInt, the number must be an integer (such that
[`Number.isInteger`](../global_objects/number/isinteger) returns true).




Examples
--------



### Invalid cases 




[js]


```js
const a = BigInt(1.5);
// RangeError: The number 1.5 cannot be converted to a BigInt because it is not an integer
const b = BigInt(NaN);
// RangeError: NaN cannot be converted to a BigInt because it is not an integer
```





### Valid cases 




[js]


```js
const a = BigInt(1);
```





See also 
--------


-   [`BigInt()` constructor](../global_objects/bigint/bigint)
-   [`Number.isInteger()`](../global_objects/number/isinteger)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Cant_be_converted_to_BigInt_because_it_isnt_an_integer>

