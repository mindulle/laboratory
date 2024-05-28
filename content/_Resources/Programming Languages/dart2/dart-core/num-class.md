[dart:core](../dart-core/dart-core-library){._links-link}

num class
=========

An integer or floating-point number.

It is a compile-time error for any type other than [int](int-class) or
[double](double-class) to attempt to extend or implement `num`.

**See also:**

-   [int](int-class): An integer number.
-   [double](double-class): A double-precision floating point number.
-   [Numbers](https://dart.dev/guides/language/numbers) in [A tour of
    the Dart language](https://dart.dev/guides/language/language-tour).

Implemented types

:   -   [Comparable](comparable-class)\<[num](num-class)\>

Implementers

:   -   [double](double-class)
    -   [int](int-class)

Constructors
------------

[num](num/num)()

Properties {#instance-properties}
----------

[hashCode](num/hashcode) → [int](int-class)

::: {.features}
read-only, override
:::

Returns a hash code for a numerical value.

[isFinite](num/isfinite) → [bool](bool-class)

::: {.features}
read-only
:::

Whether this number is finite.

[isInfinite](num/isinfinite) → [bool](bool-class)

::: {.features}
read-only
:::

Whether this number is positive infinity or negative infinity.

[isNaN](num/isnan) → [bool](bool-class)

::: {.features}
read-only
:::

Whether this number is a Not-a-Number value.

[isNegative](num/isnegative) → [bool](bool-class)

::: {.features}
read-only
:::

Whether this number is negative.

[runtimeType](object/runtimetype) → [Type](type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[sign](num/sign) → [num](num-class)

::: {.features}
read-only
:::

Negative one, zero or positive one depending on the sign and numerical
value of this number.

Methods {#instance-methods}
-------

[abs](num/abs)() → [num](num-class)

The absolute value of this number.

[ceil](num/ceil)() → [int](int-class)

The least integer no smaller than `this`.

[ceilToDouble](num/ceiltodouble)() → [double](double-class)

Returns the least double integer value no smaller than `this`.

[clamp](num/clamp)([num](num-class) lowerLimit, [num](num-class)
upperLimit) → [num](num-class)

Returns this [num](num-class) clamped to be in the range
`lowerLimit`-`upperLimit`.

[compareTo](num/compareto)([num](num-class) other) → [int](int-class)

::: {.features}
override
:::

Compares this to `other`.

[floor](num/floor)() → [int](int-class)

The greatest integer no greater than this number.

[floorToDouble](num/floortodouble)() → [double](double-class)

Returns the greatest double integer value no greater than `this`.

[noSuchMethod](object/nosuchmethod)([Invocation](invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[remainder](num/remainder)([num](num-class) other) → [num](num-class)

The remainder of the truncating division of `this` by `other`.

[round](num/round)() → [int](int-class)

The integer closest to this number.

[roundToDouble](num/roundtodouble)() → [double](double-class)

The double integer value closest to this value.

[toDouble](num/todouble)() → [double](double-class)

This number as a [double](double-class).

[toInt](num/toint)() → [int](int-class)

Truncates this [num](num-class) to an integer and returns the result as
an [int](int-class).

[toString](num/tostring)() → [String](string-class)

::: {.features}
override
:::

The shortest string that correctly represents this number.

[toStringAsExponential](num/tostringasexponential)(\[[int](int-class)?
fractionDigits\]) → [String](string-class)

An exponential string-representation of this number.

[toStringAsFixed](num/tostringasfixed)([int](int-class) fractionDigits)
→ [String](string-class)

A decimal-point string-representation of this number.

[toStringAsPrecision](num/tostringasprecision)([int](int-class)
precision) → [String](string-class)

A string representation with `precision` significant digits.

[truncate](num/truncate)() → [int](int-class)

The integer obtained by discarding any fractional digits from `this`.

[truncateToDouble](num/truncatetodouble)() → [double](double-class)

Returns the double integer value obtained by discarding any fractional
digits from the double value of `this`.

Operators
---------

[operator %](num/operator_modulo)([num](num-class) other) →
[num](num-class)

Euclidean modulo of this number by `other`.

[operator \*](num/operator_multiply)([num](num-class) other) →
[num](num-class)

Multiplies this number by `other`.

[operator +](num/operator_plus)([num](num-class) other) →
[num](num-class)

Adds `other` to this number.

[operator -](num/operator_minus)([num](num-class) other) →
[num](num-class)

Subtracts `other` from this number.

[operator /](num/operator_divide)([num](num-class) other) →
[double](double-class)

Divides this number by `other`.

[operator \<](num/operator_less)([num](num-class) other) →
[bool](bool-class)

Whether this number is numerically smaller than `other`.

[operator \<=](num/operator_less_equal)([num](num-class) other) →
[bool](bool-class)

Whether this number is numerically smaller than or equal to `other`.

[operator ==](num/operator_equals)([Object](object-class) other) →
[bool](bool-class)

::: {.features}
override
:::

Test whether this value is numerically equal to `other`.

[operator \>](num/operator_greater)([num](num-class) other) →
[bool](bool-class)

Whether this number is numerically greater than `other`.

[operator \>=](num/operator_greater_equal)([num](num-class) other) →
[bool](bool-class)

Whether this number is numerically greater than or equal to `other`.

[operator unary-](num/operator_unary_minus)() → [num](num-class)

The negation of this value.

[operator \~/](num/operator_truncate_divide)([num](num-class) other) →
[int](int-class)

Truncating division operator.

Static Methods
--------------

[parse](num/parse)([String](string-class) input, \[[num](num-class) onError([String](string-class) input)?\]) → [num](num-class)
:   Parses a string containing a number literal into a number.

[tryParse](num/tryparse)([String](string-class) input) → [num](num-class)?
:   Parses a string containing a number literal into a number.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/num-class.html>
:::
