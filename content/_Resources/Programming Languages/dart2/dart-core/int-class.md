[dart:core](../dart-core/dart-core-library){._links-link}

int class
=========

An integer number.

The default implementation of `int` is 64-bit two\'s complement integers
with operations that wrap to that range on overflow.

**Note:** When compiling to JavaScript, integers are restricted to
values that can be represented exactly by double-precision floating
point values. The available integer values include all integers between
-2\^53 and 2\^53, and some integers with larger magnitude. That includes
some integers larger than 2\^63. The behavior of the operators and
methods in the [int](int-class) class therefore sometimes differs
between the Dart VM and Dart code compiled to JavaScript. For example,
the bitwise operators truncate their operands to 32-bit integers when
compiled to JavaScript.

Classes cannot extend, implement, or mix in `int`.

**See also:**

-   [num](num-class) the super class for [int](int-class).
-   [Numbers](https://dart.dev/guides/language/numbers) in [A tour of
    the Dart language](https://dart.dev/guides/language/language-tour).

Inheritance

:   -   [Object](object-class)
    -   [num](num-class)
    -   int

Constructors
------------

[int.fromEnvironment](int/int.fromenvironment)([String](string-class)
name, {[int](int-class) defaultValue = 0})

::: {.constructor-modifier .features}
const
:::

::: {.constructor-modifier .features}
factory
:::

Returns the integer value of the given environment declaration `name`.

Properties {#instance-properties}
----------

[bitLength](int/bitlength) → [int](int-class)

::: {.features}
read-only
:::

Returns the minimum number of bits required to store this integer.

[hashCode](num/hashcode) → [int](int-class)

::: {.features}
read-only, inherited
:::

Returns a hash code for a numerical value.

[isEven](int/iseven) → [bool](bool-class)

::: {.features}
read-only
:::

Returns true if and only if this integer is even.

[isFinite](num/isfinite) → [bool](bool-class)

::: {.features}
read-only, inherited
:::

Whether this number is finite.

[isInfinite](num/isinfinite) → [bool](bool-class)

::: {.features}
read-only, inherited
:::

Whether this number is positive infinity or negative infinity.

[isNaN](num/isnan) → [bool](bool-class)

::: {.features}
read-only, inherited
:::

Whether this number is a Not-a-Number value.

[isNegative](num/isnegative) → [bool](bool-class)

::: {.features}
read-only, inherited
:::

Whether this number is negative.

[isOdd](int/isodd) → [bool](bool-class)

::: {.features}
read-only
:::

Returns true if and only if this integer is odd.

[runtimeType](object/runtimetype) → [Type](type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[sign](int/sign) → [int](int-class)

::: {.features}
read-only, override
:::

Returns the sign of this integer.

Methods {#instance-methods}
-------

[abs](int/abs)() → [int](int-class)

::: {.features}
override
:::

Returns the absolute value of this integer.

[ceil](int/ceil)() → [int](int-class)

::: {.features}
override
:::

Returns `this`.

[ceilToDouble](int/ceiltodouble)() → [double](double-class)

::: {.features}
override
:::

Returns `this.toDouble()`.

[clamp](num/clamp)([num](num-class) lowerLimit, [num](num-class)
upperLimit) → [num](num-class)

::: {.features}
inherited
:::

Returns this [num](num-class) clamped to be in the range
`lowerLimit`-`upperLimit`.

[compareTo](num/compareto)([num](num-class) other) → [int](int-class)

::: {.features}
inherited
:::

Compares this to `other`.

[floor](int/floor)() → [int](int-class)

::: {.features}
override
:::

Returns `this`.

[floorToDouble](int/floortodouble)() → [double](double-class)

::: {.features}
override
:::

Returns `this.toDouble()`.

[gcd](int/gcd)([int](int-class) other) → [int](int-class)

Returns the greatest common divisor of this integer and `other`.

[modInverse](int/modinverse)([int](int-class) modulus) →
[int](int-class)

Returns the modular multiplicative inverse of this integer modulo
`modulus`.

[modPow](int/modpow)([int](int-class) exponent, [int](int-class)
modulus) → [int](int-class)

Returns this integer to the power of `exponent` modulo `modulus`.

[noSuchMethod](object/nosuchmethod)([Invocation](invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[remainder](num/remainder)([num](num-class) other) → [num](num-class)

::: {.features}
inherited
:::

The remainder of the truncating division of `this` by `other`.

[round](int/round)() → [int](int-class)

::: {.features}
override
:::

Returns `this`.

[roundToDouble](int/roundtodouble)() → [double](double-class)

::: {.features}
override
:::

Returns `this.toDouble()`.

[toDouble](num/todouble)() → [double](double-class)

::: {.features}
inherited
:::

This number as a [double](double-class).

[toInt](num/toint)() → [int](int-class)

::: {.features}
inherited
:::

Truncates this [num](num-class) to an integer and returns the result as
an [int](int-class).

[toRadixString](int/toradixstring)([int](int-class) radix) →
[String](string-class)

Converts [this](int-class) to a string representation in the given
`radix`.

[toSigned](int/tosigned)([int](int-class) width) → [int](int-class)

Returns the least significant `width` bits of this integer, extending
the highest retained bit to the sign. This is the same as truncating the
value to fit in `width` bits using an signed 2-s complement
representation. The returned value has the same bit value in all
positions higher than `width`.

[toString](int/tostring)() → [String](string-class)

::: {.features}
override
:::

Returns a string representation of this integer.

[toStringAsExponential](num/tostringasexponential)(\[[int](int-class)?
fractionDigits\]) → [String](string-class)

::: {.features}
inherited
:::

An exponential string-representation of this number.

[toStringAsFixed](num/tostringasfixed)([int](int-class) fractionDigits)
→ [String](string-class)

::: {.features}
inherited
:::

A decimal-point string-representation of this number.

[toStringAsPrecision](num/tostringasprecision)([int](int-class)
precision) → [String](string-class)

::: {.features}
inherited
:::

A string representation with `precision` significant digits.

[toUnsigned](int/tounsigned)([int](int-class) width) → [int](int-class)

Returns the least significant `width` bits of this integer as a
non-negative number (i.e. unsigned representation). The returned value
has zeros in all bit positions higher than `width`.

[truncate](int/truncate)() → [int](int-class)

::: {.features}
override
:::

Returns `this`.

[truncateToDouble](int/truncatetodouble)() → [double](double-class)

::: {.features}
override
:::

Returns `this.toDouble()`.

Operators
---------

[operator %](num/operator_modulo)([num](num-class) other) →
[num](num-class)

::: {.features}
inherited
:::

Euclidean modulo of this number by `other`.

[operator &](int/operator_bitwise_and)([int](int-class) other) →
[int](int-class)

Bit-wise and operator.

[operator \*](num/operator_multiply)([num](num-class) other) →
[num](num-class)

::: {.features}
inherited
:::

Multiplies this number by `other`.

[operator +](num/operator_plus)([num](num-class) other) →
[num](num-class)

::: {.features}
inherited
:::

Adds `other` to this number.

[operator -](num/operator_minus)([num](num-class) other) →
[num](num-class)

::: {.features}
inherited
:::

Subtracts `other` from this number.

[operator /](num/operator_divide)([num](num-class) other) →
[double](double-class)

::: {.features}
inherited
:::

Divides this number by `other`.

[operator \<](num/operator_less)([num](num-class) other) →
[bool](bool-class)

::: {.features}
inherited
:::

Whether this number is numerically smaller than `other`.

[operator \<\<](int/operator_shift_left)([int](int-class) shiftAmount) →
[int](int-class)

Shift the bits of this integer to the left by `shiftAmount`.

[operator \<=](num/operator_less_equal)([num](num-class) other) →
[bool](bool-class)

::: {.features}
inherited
:::

Whether this number is numerically smaller than or equal to `other`.

[operator ==](num/operator_equals)([Object](object-class) other) →
[bool](bool-class)

::: {.features}
inherited
:::

Test whether this value is numerically equal to `other`.

[operator \>](num/operator_greater)([num](num-class) other) →
[bool](bool-class)

::: {.features}
inherited
:::

Whether this number is numerically greater than `other`.

[operator \>=](num/operator_greater_equal)([num](num-class) other) →
[bool](bool-class)

::: {.features}
inherited
:::

Whether this number is numerically greater than or equal to `other`.

[operator \>\>](int/operator_shift_right)([int](int-class) shiftAmount)
→ [int](int-class)

Shift the bits of this integer to the right by `shiftAmount`.

[operator \>\>\>](int/operator_triple_shift)([int](int-class)
shiftAmount) → [int](int-class)

Bitwise unsigned right shift by `shiftAmount` bits.

[operator \^](int/operator_bitwise_exclusive_or)([int](int-class) other)
→ [int](int-class)

Bit-wise exclusive-or operator.

[operator unary-](int/operator_unary_minus)() → [int](int-class)

::: {.features}
override
:::

Return the negative value of this integer.

[operator \|](int/operator_bitwise_or)([int](int-class) other) →
[int](int-class)

Bit-wise or operator.

[operator \~](int/operator_bitwise_negate)() → [int](int-class)

The bit-wise negate operator.

[operator \~/](num/operator_truncate_divide)([num](num-class) other) →
[int](int-class)

::: {.features}
inherited
:::

Truncating division operator.

Static Methods
--------------

[parse](int/parse)([String](string-class) source, {[int](int-class)?
radix, [int](int-class) onError([String](string-class) source)?}) →
[int](int-class)

::: {.features}
override
:::

Parse `source` as a, possibly signed, integer literal and return its
value.

[tryParse](int/tryparse)([String](string-class) source,
{[int](int-class)? radix}) → [int](int-class)?

::: {.features}
override
:::

Parse `source` as a, possibly signed, integer literal.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/int-class.html>
:::
