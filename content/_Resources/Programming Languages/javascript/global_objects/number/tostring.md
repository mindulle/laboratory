Number.prototype.toString()
===========================

 
The `toString()` method of [`Number`](../number) values returns a string
representing this number value.


 
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

:   An integer in the range `2` through `36` specifying the base to use
    for representing the number value. Defaults to 10.



 
### Return value 

 
A string representing the specified number value.



 
### Exceptions

 

[`RangeError`](../rangeerror)

:   Thrown if `radix` is less than 2 or greater than 36.



 
Description
-----------

 
The [`Number`](../number) object overrides the `toString` method of
[`Object`](../object); it does not inherit
[`Object.prototype.toString()`](../object/tostring). For `Number`
values, the `toString` method returns a string representation of the
value in the specified radix.

For radixes above 10, the letters of the alphabet indicate digits
greater than 9. For example, for hexadecimal numbers (base 16) `a`
through `f` are used.

If the specified number value is negative, the sign is preserved. This
is the case even if the radix is 2; the string returned is the positive
binary representation of the number value preceded by a `-` sign,
**not** the two\'s complement of the number value.

Both `0` and `-0` have `"0"` as their string representation.
[`Infinity`](../infinity) returns `"Infinity"` and [`NaN`](../nan)
returns `"NaN"`.

If the number is not a whole number, the decimal point `.` is used to
separate the decimal places. [Scientific
notation](../../lexical_grammar#exponential) is used if the radix is 10
and the number\'s magnitude (ignoring sign) is greater than or equal to
10^21^ or less than 10^-6^. In this case, the returned string always
explicitly specifies the sign of the exponent.

 
 
[js]


```js
console.log((10 ** 21.5).toString()); // "3.1622776601683794e+21"
console.log((10 ** 21.5).toString(8)); // "526665530627250154000000"
```


The `toString()` method requires its `this` value to be a `Number`
primitive or wrapper object. It throws a [`TypeError`](../typeerror) for
other `this` values without attempting to coerce them to number values.

Because `Number` doesn\'t have a
[`[@@toPrimitive]()`](../symbol/toprimitive) method, JavaScript calls
the `toString()` method automatically when a `Number` *object* is used
in a context expecting a string, such as in a [template
literal](../../template_literals). However, Number *primitive* values do
not consult the `toString()` method to be [coerced to
strings](../string#string_coercion) --- rather, they are directly
converted using the same algorithm as the initial `toString()`
implementation.

 
 
[js]


```js
Number.prototype.toString = () => "Overridden";
console.log(`${1}`); // "1"
console.log(`${new Number(1)}`); // "Overridden"
```




 
Examples
--------


 
### Using toString() 

 
 
 
[js]


```js
const count = 10;
console.log(count.toString()); // "10"

console.log((17).toString()); // "17"
console.log((17.2).toString()); // "17.2"

const x = 6;
console.log(x.toString(2)); // "110"
console.log((254).toString(16)); // "fe"
console.log((-10).toString(2)); // "-1010"
console.log((-0xff).toString(2)); // "-11111111"
```




 
### Converting radix of number strings 

 
If you have a string representing a number in a non-decimal radix, you
can use [`parseInt()`](../parseint) and `toString()` to convert it to a
different radix.

 
 
[js]


```js
const hex = "CAFEBABE";
const bin = parseInt(hex, 16).toString(2); // "11001010111111101011101010111110"
```


Beware of loss of precision: if the original number string is too large
(larger than [`Number.MAX_SAFE_INTEGER`](max_safe_integer), for
example), you should use a [`BigInt`](../bigint/bigint) instead.
However, the `BigInt` constructor only has support for strings
representing number literals (i.e. strings starting with `0b`, `0o`,
`0x`). In case your original radix is not one of binary, octal, decimal,
or hexadecimal, you may need to hand-write your radix converter, or use
a library.



Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-number.prototype.tostring]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-number.prototype.tostring)

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

 
-   [`Number.prototype.toFixed()`](tofixed)
-   [`Number.prototype.toExponential()`](toexponential)
-   [`Number.prototype.toPrecision()`](toprecision)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toString>

