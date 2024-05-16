BigInt() constructor
====================

Baseline [Widely available]
--------------------------------------


This feature is well established and works across many devices and
browser versions. It's been available across browsers since September
2020.

-   [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-evolution-on-mdn/)
-   [See full compatibility](#browser_compatibility)
-   [Report
    feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FJavaScript%2FReference%2FGlobal_Objects%2FBigInt%2FBigInt&level=high)



The `BigInt()` function returns primitive values of type BigInt.



Syntax
------




[js]


```js
BigInt(value)
```


 
**Note:** `BigInt()` can only be called without
[`new`](../../operators/new). Attempting to construct it with `new`
throws a [`TypeError`](../typeerror).





### Parameters



[`value`](#value)

:   The value to be converted to a BigInt value. It may be a string, an
    integer, a boolean, or another `BigInt`.




### Return value 


A [`BigInt`](../bigint) value. Number values must be integers and are
converted to BigInts. The boolean value `true` becomes `1n`, and `false`
becomes `0n`. Strings are parsed as if they are source text for integer
literals, which means they can have leading and trailing whitespaces and
can be prefixed with `0b`, `0o`, or `0x`.




### Exceptions



[`RangeError`](../rangeerror)

:   Thrown if the parameter is a non-integral number.

[`TypeError`](../typeerror)

:   Thrown in one of the following cases:

    -   The parameter cannot be converted to a primitive.
    -   After conversion to a primitive, the result is
        [`undefined`](../undefined), [`null`](../../operators/null),
        [`symbol`](../symbol).

[`SyntaxError`](../syntaxerror)

:   Thrown if the parameter is a string that cannot be parsed as a
    `BigInt`.




Examples
--------



### Using BigInt() to convert a number to a BigInt 


`BigInt()` is the only case where a number can be converted to a BigInt
without throwing, because it\'s very explicit. However, only integers
are allowed.



[js]


```js
BigInt(123); // 123n
BigInt(123.3); // RangeError: The number 123.3 cannot be converted to a BigInt because it is not an integer
```





### Using string values 




[js]


```js
BigInt("123"); // 123n
BigInt("0b10101"); // 21n, which is 10101 in binary
BigInt("0o123"); // 83n, which is 123 in octal
BigInt("0x123"); // 291n, which is 123 in hexadecimal
BigInt("  123  "); // 123n, leading and trailing whitespaces are allowed
```




Specifications
--------------


  -------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-bigint-constructor]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-bigint-constructor)

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

`BigInt`

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




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/BigInt/BigInt>

