BigInt.prototype.toString()
===========================

Baseline [Widely available]
--------------------------------------


This feature is well established and works across many devices and
browser versions. It's been available across browsers since September
2020.

-   [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-evolution-on-mdn/)
-   [See full compatibility](#browser_compatibility)
-   [Report
    feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FJavaScript%2FReference%2FGlobal_Objects%2FBigInt%2FtoString&level=high)



The `toString()` method of [`BigInt`](../bigint) values returns a string
representing the specified [`BigInt`](../bigint) value. The trailing
\"n\" is not part of the string.



Try it 
------






Syntax
------




[js]


```js
toString()
toString(radix)
```





### Parameters



[`radix`](#radix) [Optional]

:   An integer in the range 2 through 36 specifying the base to use for
    representing the BigInt value. Defaults to 10.




### Return value 


A string representing the specified [`BigInt`](../bigint) value.




### Exceptions



[`RangeError`](../rangeerror)

:   Thrown if `radix` is less than 2 or greater than 36.




Description
-----------


The [`BigInt`](../bigint) object overrides the `toString` method of
[`Object`](../object); it does not inherit
[`Object.prototype.toString()`](../object/tostring). For
[`BigInt`](../bigint) values, the `toString()` method returns a string
representation of the value in the specified radix.

For radixes above 10, the letters of the alphabet indicate digits
greater than 9. For example, for hexadecimal numbers (base 16) `a`
through `f` are used.

If the specified BigInt value is negative, the sign is preserved. This
is the case even if the radix is 2; the string returned is the positive
binary representation of the BigInt value preceded by a `-` sign,
**not** the two\'s complement of the BigInt value.

The `toString()` method requires its `this` value to be a `BigInt`
primitive or wrapper object. It throws a [`TypeError`](../typeerror) for
other `this` values without attempting to coerce them to BigInt values.

Because `BigInt` doesn\'t have a
[`[@@toPrimitive]()`](../symbol/toprimitive) method, JavaScript calls
the `toString()` method automatically when a `BigInt` *object* is used
in a context expecting a string, such as in a [template
literal](../../template_literals). However, BigInt *primitive* values do
not consult the `toString()` method to be [coerced to
strings](../string#string_coercion) --- rather, they are directly
converted using the same algorithm as the initial `toString()`
implementation.



[js]


```js
BigInt.prototype.toString = () => "Overridden";
console.log(`${1n}`); // "1"
console.log(`${Object(1n)}`); // "Overridden"
```





Examples
--------



### Using toString() 




[js]


```js
17n.toString(); // "17"
66n.toString(2); // "1000010"
254n.toString(16); // "fe"
(-10n).toString(2); // "-1010"
(-0xffn).toString(2); // "-11111111"
```





### Negative-zero BigInt 


There is no negative-zero `BigInt` as there are no negative zeros in
integers. `-0.0` is an IEEE floating-point concept that only appears in
the JavaScript
[`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#number_type)
type.



[js]


```js
(-0n).toString(); // "0"
BigInt(-0).toString(); // "0"
```




Specifications
--------------


  ---------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-bigint.prototype.tostring]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-bigint.prototype.tostring)

  ---------------------------------------------------------------------------------------------------------------------------------


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

`toString`

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


-   [`BigInt.prototype.toLocaleString()`](tolocalestring)
-   [`BigInt.prototype.valueOf()`](valueof)
-   [`Number.prototype.toString()`](../number/tostring)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/BigInt/toString>

