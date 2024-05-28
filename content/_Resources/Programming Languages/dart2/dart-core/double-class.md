[dart:core](../dart-core/dart-core-library){._links-link}

double class
============

A double-precision floating point number.

Representation of Dart doubles containing double specific constants and
operations and specializations of operations inherited from
[num](num-class). Dart doubles are 64-bit floating-point numbers as
specified in the IEEE 754 standard.

The [double](double-class) type is contagious. Operations on
[double](double-class)s return [double](double-class) results.

It is a compile-time error for a class to attempt to extend or implement
double.

**See also:**

-   [num](num-class) the super class for [double](double-class).
-   [Numbers](https://dart.dev/guides/language/numbers) in [A tour of
    the Dart language](https://dart.dev/guides/language/language-tour).

Inheritance

:   -   [Object](object-class)
    -   [num](num-class)
    -   double

Constructors
------------

[double](double/double)()

Properties {#instance-properties}
----------

[hashCode](num/hashcode) → [int](int-class)

::: {.features}
read-only, inherited
:::

Returns a hash code for a numerical value.

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

[runtimeType](object/runtimetype) → [Type](type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[sign](double/sign) → [double](double-class)

::: {.features}
read-only, override
:::

The sign of the double\'s numerical value.

Methods {#instance-methods}
-------

[abs](double/abs)() → [double](double-class)

::: {.features}
override
:::

The absolute value of this number.

[ceil](double/ceil)() → [int](int-class)

::: {.features}
override
:::

Returns the least integer that is not smaller than this number.

[ceilToDouble](double/ceiltodouble)() → [double](double-class)

::: {.features}
override
:::

Returns the least integer double value no smaller than `this`.

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

[floor](double/floor)() → [int](int-class)

::: {.features}
override
:::

Returns the greatest integer no greater than this number.

[floorToDouble](double/floortodouble)() → [double](double-class)

::: {.features}
override
:::

Returns the greatest integer double value no greater than `this`.

[noSuchMethod](object/nosuchmethod)([Invocation](invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[remainder](double/remainder)([num](num-class) other) →
[double](double-class)

::: {.features}
override
:::

The remainder of the truncating division of `this` by `other`.

[round](double/round)() → [int](int-class)

::: {.features}
override
:::

Returns the integer closest to this number.

[roundToDouble](double/roundtodouble)() → [double](double-class)

::: {.features}
override
:::

Returns the integer double value closest to `this`.

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

[toString](double/tostring)() → [String](string-class)

::: {.features}
override
:::

Provide a representation of this [double](double-class) value.

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

[truncate](double/truncate)() → [int](int-class)

::: {.features}
override
:::

Returns the integer obtained by discarding any fractional part of this
number.

[truncateToDouble](double/truncatetodouble)() → [double](double-class)

::: {.features}
override
:::

Returns the integer double value obtained by discarding any fractional
digits from `this`.

Operators
---------

[operator %](double/operator_modulo)([num](num-class) other) →
[double](double-class)

::: {.features}
override
:::

Euclidean modulo of this number by `other`.

[operator \*](double/operator_multiply)([num](num-class) other) →
[double](double-class)

::: {.features}
override
:::

Multiplies this number by `other`.

[operator +](double/operator_plus)([num](num-class) other) →
[double](double-class)

::: {.features}
override
:::

Adds `other` to this number.

[operator -](double/operator_minus)([num](num-class) other) →
[double](double-class)

::: {.features}
override
:::

Subtracts `other` from this number.

[operator /](double/operator_divide)([num](num-class) other) →
[double](double-class)

::: {.features}
override
:::

Divides this number by `other`.

[operator \<](num/operator_less)([num](num-class) other) →
[bool](bool-class)

::: {.features}
inherited
:::

Whether this number is numerically smaller than `other`.

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

[operator unary-](double/operator_unary_minus)() →
[double](double-class)

::: {.features}
override
:::

The negation of this value.

[operator \~/](double/operator_truncate_divide)([num](num-class) other)
→ [int](int-class)

::: {.features}
override
:::

Truncating division operator.

Static Methods
--------------

[parse](double/parse)([String](string-class) source,
\[[double](double-class) onError([String](string-class) source)?\]) →
[double](double-class)

::: {.features}
override
:::

Parse `source` as a double literal and return its value.

[tryParse](double/tryparse)([String](string-class) source) →
[double](double-class)?

::: {.features}
override
:::

Parse `source` as a double literal and return its value.

Constants
---------

[infinity](double/infinity-constant) → const [double](double-class)

:   <div>

    `1.0 / 0.0`

    </div>

[maxFinite](double/maxfinite-constant) → const [double](double-class)

:   <div>

    `1.7976931348623157e+308`

    </div>

[minPositive](double/minpositive-constant) → const [double](double-class)

:   <div>

    `5e-324`

    </div>

[nan](double/nan-constant) → const [double](double-class)

:   <div>

    `0.0 / 0.0`

    </div>

[negativeInfinity](double/negativeinfinity-constant) → const [double](double-class)

:   <div>

    `-infinity`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/double-class.html>
:::
