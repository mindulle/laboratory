Number() constructor
====================

 
The `Number()` constructor creates [`Number`](../number) objects. When
called as a function, it returns primitive values of type Number.


 
Syntax
------

 
 
 
[js]


```js
new Number(value)
Number(value)
```


 
**Note:** `Number()` can be called with or without
[`new`](../../operators/new), but with different effects. See [Return
value](#return_value).




 
### Parameters

 

[`value`](#value)

:   The numeric value of the object being created.



 
### Return value 

 
When `Number` is called as a constructor (with
[`new`](../../operators/new)), it creates a [`Number`](../number)
object, which is **not** a primitive.

When `Number` is called as a function, it [coerces the parameter to a
number primitive](../number#number_coercion). [BigInts](../bigint) are
converted to numbers. If the value can\'t be converted, it returns
[`NaN`](../nan).

 
**Warning:** You should rarely find yourself using `Number` as a
constructor.




 
Examples
--------


 
### Creating Number objects 

 
 
 
[js]


```js
const a = new Number("123"); // a === 123 is false
const b = Number("123"); // b === 123 is true
a instanceof Number; // is true
b instanceof Number; // is false
typeof a; // "object"
typeof b; // "number"
```




 
### Using Number() to convert a BigInt to a number 

 
`Number()` is the only case where a BigInt can be converted to a number
without throwing, because it\'s very explicit.

 
 
[js]


```js
+1n; // TypeError: Cannot convert a BigInt value to a number
0 + 1n; // TypeError: Cannot mix BigInt and other types, use explicit conversions
```


 
 
[js]


```js
Number(1n); // 1
```


Note that this may result in loss of precision, if the BigInt is too
large to be [safely represented](issafeinteger).

 
 
[js]


```js
BigInt(Number(2n ** 54n + 1n)) === 2n ** 54n + 1n; // false
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-number-constructor]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-number-constructor)

  -------------------------------------------------------------------------------------------------------------------


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

`Number`

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

 
-   [Polyfill of modern `Number` behavior (with support binary and octal
    literals) in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-number)
-   [`NaN`](../nan)
-   [`Math`](../math)
-   [`BigInt`](../bigint)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/Number>

