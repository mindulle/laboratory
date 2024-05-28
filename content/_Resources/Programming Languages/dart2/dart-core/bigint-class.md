[dart:core](../dart-core/dart-core-library){._links-link}

BigInt class
============

An arbitrarily large integer value.

Big integers are signed and can have an arbitrary number of significant
digits, only limited by memory.

To create a big integer from the provided number, use
[BigInt.from](bigint/bigint.from).

``` {.language-dart data-language="dart"}
var bigInteger = BigInt.from(-1); // -1
bigInteger = BigInt.from(0.9999); // 0
bigInteger = BigInt.from(-10.99); // -10
bigInteger = BigInt.from(0x7FFFFFFFFFFFFFFF); // 9223372036854775807
bigInteger = BigInt.from(1e+30); // 1000000000000000019884624838656
```

To parse a large integer value from a string, use [parse](bigint/parse)
or [tryParse](bigint/tryparse).

``` {.language-dart data-language="dart"}
var value = BigInt.parse('0x1ffffffffffffffff'); // 36893488147419103231
value = BigInt.parse('12345678901234567890'); // 12345678901234567890
```

To check whether a big integer can be represented as an [int](int-class)
without losing precision, use [isValidInt](bigint/isvalidint).

``` {.language-dart data-language="dart"}
print(bigNumber.isValidInt); // false
```

To convert a big integer into an [int](int-class), use
[toInt](bigint/toint). To convert a big integer into an
[double](double-class), use [toDouble](bigint/todouble).

``` {.language-dart data-language="dart"}
var bigValue = BigInt.from(10).pow(3);
print(bigValue.isValidInt); // true
print(bigValue.toInt()); // 1000
print(bigValue.toDouble()); // 1000.0
```

**See also:**

-   [int](int-class): An integer number.
-   [double](double-class): A double-precision floating point number.
-   [num](num-class): The super class for [int](int-class) and
    [double](double-class).
-   [Numbers](https://dart.dev/guides/language/numbers) in [A tour of
    the Dart language](https://dart.dev/guides/language/language-tour).

Implemented types

:   -   [Comparable](comparable-class)\<[BigInt](bigint-class)\>

Constructors
------------

[BigInt.from](bigint/bigint.from)([num](num-class) value)

::: {.constructor-modifier .features}
factory
:::

Creates a big integer from the provided `value` number.

Properties {#instance-properties}
----------

[bitLength](bigint/bitlength) → [int](int-class)

::: {.features}
read-only
:::

Returns the minimum number of bits required to store this big integer.

[hashCode](object/hashcode) → [int](int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isEven](bigint/iseven) → [bool](bool-class)

::: {.features}
read-only
:::

Whether this big integer is even.

[isNegative](bigint/isnegative) → [bool](bool-class)

::: {.features}
read-only
:::

Whether this number is negative.

[isOdd](bigint/isodd) → [bool](bool-class)

::: {.features}
read-only
:::

Whether this big integer is odd.

[isValidInt](bigint/isvalidint) → [bool](bool-class)

::: {.features}
read-only
:::

Whether this big integer can be represented as an `int` without losing
precision.

[runtimeType](object/runtimetype) → [Type](type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[sign](bigint/sign) → [int](int-class)

::: {.features}
read-only
:::

Returns the sign of this big integer.

Methods {#instance-methods}
-------

[abs](bigint/abs)() → [BigInt](bigint-class)

Returns the absolute value of this integer.

[compareTo](bigint/compareto)([BigInt](bigint-class) other) →
[int](int-class)

::: {.features}
override
:::

Compares this to `other`.

[gcd](bigint/gcd)([BigInt](bigint-class) other) → [BigInt](bigint-class)

Returns the greatest common divisor of this big integer and `other`.

[modInverse](bigint/modinverse)([BigInt](bigint-class) modulus) →
[BigInt](bigint-class)

Returns the modular multiplicative inverse of this big integer modulo
`modulus`.

[modPow](bigint/modpow)([BigInt](bigint-class) exponent,
[BigInt](bigint-class) modulus) → [BigInt](bigint-class)

Returns this integer to the power of `exponent` modulo `modulus`.

[noSuchMethod](object/nosuchmethod)([Invocation](invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[pow](bigint/pow)([int](int-class) exponent) → [BigInt](bigint-class)

Returns `this` to the power of `exponent`.

[remainder](bigint/remainder)([BigInt](bigint-class) other) →
[BigInt](bigint-class)

Returns the remainder of the truncating division of `this` by `other`.

[toDouble](bigint/todouble)() → [double](double-class)

Returns this [BigInt](bigint-class) as a [double](double-class).

[toInt](bigint/toint)() → [int](int-class)

Returns this [BigInt](bigint-class) as an [int](int-class).

[toRadixString](bigint/toradixstring)([int](int-class) radix) →
[String](string-class)

Converts [this](bigint-class) to a string representation in the given
`radix`.

[toSigned](bigint/tosigned)([int](int-class) width) →
[BigInt](bigint-class)

Returns the least significant `width` bits of this integer, extending
the highest retained bit to the sign. This is the same as truncating the
value to fit in `width` bits using an signed 2-s complement
representation. The returned value has the same bit value in all
positions higher than `width`.

[toString](bigint/tostring)() → [String](string-class)

::: {.features}
override
:::

Returns a String-representation of this integer.

[toUnsigned](bigint/tounsigned)([int](int-class) width) →
[BigInt](bigint-class)

Returns the least significant `width` bits of this big integer as a
non-negative number (i.e. unsigned representation). The returned value
has zeros in all bit positions higher than `width`.

Operators
---------

[operator %](bigint/operator_modulo)([BigInt](bigint-class) other) →
[BigInt](bigint-class)

Euclidean modulo operator.

[operator &](bigint/operator_bitwise_and)([BigInt](bigint-class) other)
→ [BigInt](bigint-class)

Bit-wise and operator.

[operator \*](bigint/operator_multiply)([BigInt](bigint-class) other) →
[BigInt](bigint-class)

Multiplies `other` by this big integer.

[operator +](bigint/operator_plus)([BigInt](bigint-class) other) →
[BigInt](bigint-class)

Adds `other` to this big integer.

[operator -](bigint/operator_minus)([BigInt](bigint-class) other) →
[BigInt](bigint-class)

Subtracts `other` from this big integer.

[operator /](bigint/operator_divide)([BigInt](bigint-class) other) →
[double](double-class)

Double division operator.

[operator \<](bigint/operator_less)([BigInt](bigint-class) other) →
[bool](bool-class)

Whether this big integer is numerically smaller than `other`.

[operator \<\<](bigint/operator_shift_left)([int](int-class)
shiftAmount) → [BigInt](bigint-class)

Shift the bits of this integer to the left by `shiftAmount`.

[operator \<=](bigint/operator_less_equal)([BigInt](bigint-class) other)
→ [bool](bool-class)

Whether `other` is numerically greater than this big integer.

[operator ==](object/operator_equals)([Object](object-class) other) →
[bool](bool-class)

::: {.features}
inherited
:::

The equality operator.

[operator \>](bigint/operator_greater)([BigInt](bigint-class) other) →
[bool](bool-class)

Whether this big integer is numerically greater than `other`.

[operator \>=](bigint/operator_greater_equal)([BigInt](bigint-class)
other) → [bool](bool-class)

Whether `other` is numerically smaller than this big integer.

[operator \>\>](bigint/operator_shift_right)([int](int-class)
shiftAmount) → [BigInt](bigint-class)

Shift the bits of this integer to the right by `shiftAmount`.

[operator
\^](bigint/operator_bitwise_exclusive_or)([BigInt](bigint-class) other)
→ [BigInt](bigint-class)

Bit-wise exclusive-or operator.

[operator unary-](bigint/operator_unary_minus)() →
[BigInt](bigint-class)

Return the negative value of this integer.

[operator \|](bigint/operator_bitwise_or)([BigInt](bigint-class) other)
→ [BigInt](bigint-class)

Bit-wise or operator.

[operator \~](bigint/operator_bitwise_negate)() → [BigInt](bigint-class)

The bit-wise negate operator.

[operator \~/](bigint/operator_truncate_divide)([BigInt](bigint-class)
other) → [BigInt](bigint-class)

Truncating integer division operator.

Static Properties
-----------------

[one](bigint/one) → [BigInt](bigint-class)

::: {.features}
read-only
:::

A big integer with the numerical value 1.

[two](bigint/two) → [BigInt](bigint-class)

::: {.features}
read-only
:::

A big integer with the numerical value 2.

[zero](bigint/zero) → [BigInt](bigint-class)

::: {.features}
read-only
:::

A big integer with the numerical value 0.

Static Methods
--------------

[parse](bigint/parse)([String](string-class) source, {[int](int-class)? radix}) → [BigInt](bigint-class)
:   Parses `source` as a, possibly signed, integer literal and returns
    its value.

[tryParse](bigint/tryparse)([String](string-class) source, {[int](int-class)? radix}) → [BigInt](bigint-class)?
:   Parses `source` as a, possibly signed, integer literal and returns
    its value.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/BigInt-class.html>
:::
