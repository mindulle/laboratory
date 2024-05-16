Number
======

 
`Number` values represent floating-point numbers like `37` or `-9.25`.

The `Number` constructor contains constants and methods for working with
numbers. Values of other types can be converted to numbers using the
`Number()` function.


 
Description
-----------

 
Numbers are most commonly expressed in literal forms like `255` or
`3.14159`. The [lexical grammar](../lexical_grammar#numeric_literals)
contains a more detailed reference.

 
 
[js]


```js
255; // two-hundred and fifty-five
255.0; // same number
255 === 255.0; // true
255 === 0xff; // true (hexadecimal notation)
255 === 0b11111111; // true (binary notation)
255 === 0.255e3; // true (decimal exponential notation)
```


A number literal like `37` in JavaScript code is a floating-point value,
not an integer. There is no separate integer type in common everyday
use. (JavaScript also has a [`BigInt`](bigint) type, but it\'s not
designed to replace Number for everyday uses. `37` is still a number,
not a BigInt.)

When used as a function, `Number(value)` converts a string or other
value to the Number type. If the value can\'t be converted, it returns
[`NaN`](nan).

 
 
[js]


```js
Number("123"); // returns the number 123
Number("123") === 123; // true

Number("unicorn"); // NaN
Number(undefined); // NaN
```




 
### Number encoding 

 
The JavaScript `Number` type is a [double-precision 64-bit binary format
IEEE
754](https://en.wikipedia.org/wiki/Double_precision_floating-point_format)
value, like `double` in Java or C\#. This means it can represent
fractional values, but there are some limits to the stored number\'s
magnitude and precision. Very briefly, an IEEE 754 double-precision
number uses 64 bits to represent 3 parts:

-   1 bit for the *sign* (positive or negative)
-   11 bits for the *exponent* (-1022 to 1023)
-   52 bits for the *mantissa* (representing a number between 0 and 1)

The mantissa (also called *significand*) is the part of the number
representing the actual value (significant digits). The exponent is the
power of 2 that the mantissa should be multiplied by. Thinking about it
as scientific notation:

$$\text{Number} = ({- 1})^{\text{sign}} \cdot (1 + \text{mantissa}) \cdot 2^{\text{exponent}}$$

The mantissa is stored with 52 bits, interpreted as digits after `1.…`
in a binary fractional number. Therefore, the mantissa\'s precision is
2^-52^ (obtainable via [`Number.EPSILON`](number/epsilon)), or about 15
to 17 decimal places; arithmetic above that level of precision is
subject to
[rounding](https://en.wikipedia.org/wiki/Floating-point_arithmetic#Representable_numbers,_conversion_and_rounding).

The largest value a number can hold is 2^1023^ × (2 - 2^-52^) (with the
exponent being 1023 and the mantissa being 0.1111... in base 2), which
is obtainable via [`Number.MAX_VALUE`](number/max_value). Values higher
than that are replaced with the special number constant
[`Infinity`](infinity).

Integers can only be represented without loss of precision in the range
-2^53^ + 1 to 2^53^ - 1, inclusive (obtainable via
[`Number.MIN_SAFE_INTEGER`](number/min_safe_integer) and
[`Number.MAX_SAFE_INTEGER`](number/max_safe_integer)), because the
mantissa can only hold 53 bits (including the leading 1).

More details on this are described in the [ECMAScript
standard](https://tc39.es/ecma262/multipage/ecmascript-data-types-and-values.html#sec-ecmascript-language-types-number-type).



 
### Number coercion 

 
Many built-in operations that expect numbers first coerce their
arguments to numbers (which is largely why `Number` objects behave
similarly to number primitives). [The
operation](https://tc39.es/ecma262/multipage/abstract-operations.html#sec-tonumber)
can be summarized as follows:

-   Numbers are returned as-is.
-   [`undefined`](undefined) turns into [`NaN`](nan).
-   [`null`](../operators/null) turns into `0`.
-   `true` turns into `1`; `false` turns into `0`.
-   Strings are converted by parsing them as if they contain a [number
    literal](../lexical_grammar#numeric_literals). Parsing failure
    results in `NaN`. There are some minor differences compared to an
    actual number literal:
    -   Leading and trailing whitespace/line terminators are ignored.
    -   A leading `0` digit does not cause the number to become an octal
        literal (or get rejected in strict mode).
    -   `+` and `-` are allowed at the start of the string to indicate
        its sign. (In actual code, they \"look like\" part of the
        literal, but are actually separate unary operators.) However,
        the sign can only appear once, and must not be followed by
        whitespace.
    -   `Infinity` and `-Infinity` are recognized as literals. In actual
        code, they are global variables.
    -   Empty or whitespace-only strings are converted to `0`.
    -   [Numeric separators](../lexical_grammar#numeric_separators) are
        not allowed.
-   [BigInts](bigint) throw a [`TypeError`](typeerror) to prevent
    unintended implicit coercion causing loss of precision.
-   [Symbols](symbol) throw a [`TypeError`](typeerror).
-   Objects are first [converted to a
    primitive](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#primitive_coercion)
    by calling their [`[@@toPrimitive]()`](symbol/toprimitive) (with
    `"number"` as hint), `valueOf()`, and `toString()` methods, in that
    order. The resulting primitive is then converted to a number.

There are two ways to achieve nearly the same effect in JavaScript.

-   [Unary plus](../operators/unary_plus): `+x` does exactly the number
    coercion steps explained above to convert `x`.
-   The [`Number()`](number/number) function: `Number(x)` uses the same
    algorithm to convert `x`, except that [BigInts](bigint) don\'t throw
    a [`TypeError`](typeerror), but return their number value, with
    possible loss of precision.

[`Number.parseFloat()`](number/parsefloat) and
[`Number.parseInt()`](number/parseint) are similar to `Number()` but
only convert strings, and have slightly different parsing rules. For
example, `parseInt()` doesn\'t recognize the decimal point, and
`parseFloat()` doesn\'t recognize the `0x` prefix.

#### Integer conversion 

Some operations expect integers, most notably those that work with
array/string indices, date/time components, and number radixes. After
performing the number coercion steps above, the result is
[truncated](math/trunc) to an integer (by discarding the fractional
part). If the number is ±Infinity, it\'s returned as-is. If the number
is `NaN` or `-0`, it\'s returned as `0`. The result is therefore always
an integer (which is not `-0`) or ±Infinity.

Notably, when converted to integers, both `undefined` and `null` become
`0`, because `undefined` is converted to `NaN`, which also becomes `0`.

#### Fixed-width number conversion 

JavaScript has some lower-level functions that deal with the binary
encoding of integer numbers, most notably [bitwise
operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#bitwise_shift_operators)
and [`TypedArray`](typedarray) objects. Bitwise operators always convert
the operands to 32-bit integers. In these cases, after converting the
value to a number, the number is then normalized to the given width by
first [truncating](math/trunc) the fractional part and then taking the
lowest bits in the integer\'s two\'s complement encoding.

 
 
[js]


```js
new Int32Array([1.1, 1.9, -1.1, -1.9]); // Int32Array(4) [ 1, 1, -1, -1 ]

new Int8Array([257, -257]); // Int8Array(2) [ 1, -1 ]
// 257 = 0001 0000 0001
//     =      0000 0001 (mod 2^8)
//     = 1
// -257 = 1110 1111 1111
//      =      1111 1111 (mod 2^8)
//      = -1 (as signed integer)

new Uint8Array([257, -257]); // Uint8Array(2) [ 1, 255 ]
// -257 = 1110 1111 1111
//      =      1111 1111 (mod 2^8)
//      = 255 (as unsigned integer)
```




 
Constructor
-----------

 

[`Number()`](number/number)

:   Creates a new `Number` value.

When `Number` is called as a constructor (with `new`), it creates a
[`Number`](number) object, which is **not** a primitive. For example,
`typeof new Number(42) === "object"`, and `new Number(42) !== 42`
(although `new Number(42) == 42`).

 
**Warning:** You should rarely find yourself using `Number` as a
constructor.




 
Static properties 
-----------------

 

[`Number.EPSILON`](number/epsilon)

:   The smallest interval between two representable numbers.

[`Number.MAX_SAFE_INTEGER`](number/max_safe_integer)

:   The maximum safe integer in JavaScript (2^53^ - 1).

[`Number.MAX_VALUE`](number/max_value)

:   The largest positive representable number.

[`Number.MIN_SAFE_INTEGER`](number/min_safe_integer)

:   The minimum safe integer in JavaScript (-(2^53^ - 1)).

[`Number.MIN_VALUE`](number/min_value)

:   The smallest positive representable number---that is, the positive
    number closest to zero (without actually being zero).

[`Number.NaN`](number/nan)

:   Special \"**N**ot **a** **N**umber\" value.

[`Number.NEGATIVE_INFINITY`](number/negative_infinity)

:   Special value representing negative infinity. Returned on overflow.

[`Number.POSITIVE_INFINITY`](number/positive_infinity)

:   Special value representing infinity. Returned on overflow.



 
Static methods 
--------------

 

[`Number.isFinite()`](number/isfinite)

:   Determine whether the passed value is a finite number.

[`Number.isInteger()`](number/isinteger)

:   Determine whether the passed value is an integer.

[`Number.isNaN()`](number/isnan)

:   Determine whether the passed value is `NaN`.

[`Number.isSafeInteger()`](number/issafeinteger)

:   Determine whether the passed value is a safe integer (number between
    -(2^53^ - 1) and 2^53^ - 1).

[`Number.parseFloat()`](number/parsefloat)

:   This is the same as the global [`parseFloat()`](parsefloat)
    function.

[`Number.parseInt()`](number/parseint)

:   This is the same as the global [`parseInt()`](parseint) function.



 
Instance properties 
-------------------

 
These properties are defined on `Number.prototype` and shared by all
`Number` instances.

[`Number.prototype.constructor`](object/constructor)

:   The constructor function that created the instance object. For
    `Number` instances, the initial value is the
    [`Number`](number/number) constructor.



 
Instance methods 
----------------

 

[`Number.prototype.toExponential()`](number/toexponential)

:   Returns a string representing the number in exponential notation.

[`Number.prototype.toFixed()`](number/tofixed)

:   Returns a string representing the number in fixed-point notation.

[`Number.prototype.toLocaleString()`](number/tolocalestring)

:   Returns a string with a language sensitive representation of this
    number. Overrides the
    [`Object.prototype.toLocaleString()`](object/tolocalestring) method.

[`Number.prototype.toPrecision()`](number/toprecision)

:   Returns a string representing the number to a specified precision in
    fixed-point or exponential notation.

[`Number.prototype.toString()`](number/tostring)

:   Returns a string representing the specified object in the specified
    *radix* (\"base\"). Overrides the
    [`Object.prototype.toString()`](object/tostring) method.

[`Number.prototype.valueOf()`](number/valueof)

:   Returns the primitive value of the specified object. Overrides the
    [`Object.prototype.valueOf()`](object/valueof) method.



 
Examples
--------


 
### Using the Number object to assign values to numeric variables 

 
The following example uses the `Number` object\'s properties to assign
values to several numeric variables:

 
 
[js]


```js
const biggestNum = Number.MAX_VALUE;
const smallestNum = Number.MIN_VALUE;
const infiniteNum = Number.POSITIVE_INFINITY;
const negInfiniteNum = Number.NEGATIVE_INFINITY;
const notANum = Number.NaN;
```




 
### Integer range for Number 

 
The following example shows the minimum and maximum integer values that
can be represented as `Number` object.

 
 
[js]


```js
const biggestInt = Number.MAX_SAFE_INTEGER; // (2**53 - 1) => 9007199254740991
const smallestInt = Number.MIN_SAFE_INTEGER; // -(2**53 - 1) => -9007199254740991
```


When parsing data that has been serialized to JSON, integer values
falling outside of this range can be expected to become corrupted when
JSON parser coerces them to `Number` type.

A possible workaround is to use [`String`](string) instead.

Larger numbers can be represented using the [`BigInt`](bigint) type.



 
### Using Number() to convert a Date object 

 
The following example converts the [`Date`](date) object to a numerical
value using `Number` as a function:

 
 
[js]


```js
const d = new Date("1995-12-17T03:24:00");
console.log(Number(d));
```


This logs `819199440000`.



 
### Convert numeric strings and null to numbers 

 
 
 
[js]


```js
Number("123"); // 123
Number("123") === 123; // true
Number("12.3"); // 12.3
Number("12.00"); // 12
Number("123e-1"); // 12.3
Number(""); // 0
Number(null); // 0
Number("0x11"); // 17
Number("0b11"); // 3
Number("0o11"); // 9
Number("foo"); // NaN
Number("100a"); // NaN
Number("-Infinity"); // -Infinity
```




Specifications
--------------

 
  -----------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-number-objects]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-number-objects)

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

`EPSILON`

34

12

25

21

9

34

25

21

9

2.0

37

1.0

0.12.0

`MAX_SAFE_INTEGER`

34

12

31

21

9

34

31

21

9

2.0

37

1.0

0.12.0

`MAX_VALUE`

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

`MIN_SAFE_INTEGER`

34

12

31

21

9

34

31

21

9

2.0

37

1.0

0.12.0

`MIN_VALUE`

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

`NEGATIVE_INFINITY`

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

`NaN`

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

`POSITIVE_INFINITY`

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

`isFinite`

19

12

16

15

9

25

16

14

9

1.5

4.4

1.0

0.10.0

`isInteger`

34

12

16

21

9

34

16

21

9

2.0

37

1.0

0.12.0

`isNaN`

25

12

15

15

9

25

15

14

9

1.5

4.4

1.0

0.10.0

`isSafeInteger`

34

12

32

21

9

34

32

21

9

2.0

37

1.0

0.12.0

`parseFloat`

34

12

25

21

9

34

25

21

9

2.0

37

1.0

0.12.0

`parseInt`

34

12

25

21

9

34

25

21

9

2.0

37

1.0

0.12.0

`toExponential`

1

12

1

7

2

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`toFixed`

1

12

1

7

2

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`toLocaleString`

1

12Before Edge 18, numbers are rounded to 15 decimal digits. For example,
`(1000000000000005).toLocaleString('en-US')` returns
`"1,000,000,000,000,010"`.

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

`toPrecision`

1

12

1

7

2

18

4

10.1

1

1.0

4.4

1.0

0.10.0

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

`valueOf`

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

 
-   [Polyfill of modern `Number` behavior (with support binary and octal
    literals) in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-number)
-   [`NaN`](nan)
-   [Arithmetic
    operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#arithmetic_operators)
-   [`Math`](math)
-   [`BigInt`](bigint)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number>

