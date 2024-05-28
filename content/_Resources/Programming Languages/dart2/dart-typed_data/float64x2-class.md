[dart:typed\_data](../dart-typed_data/dart-typed_data-library){._links-link}

Float64x2 class
===============

Float64x2 immutable value type and operations.

Float64x2 stores 2 64-bit floating point values in \"lanes\". The lanes
are \"x\" and \"y\" respectively.

Constructors
------------

[Float64x2](float64x2/float64x2)([double](../dart-core/double-class) x,
[double](../dart-core/double-class) y)

::: {.constructor-modifier .features}
factory
:::

[Float64x2.fromFloat32x4](float64x2/float64x2.fromfloat32x4)([Float32x4](float32x4-class)
v)

::: {.constructor-modifier .features}
factory
:::

Uses the \"x\" and \"y\" lanes from `v`.

[Float64x2.splat](float64x2/float64x2.splat)([double](../dart-core/double-class)
v)

::: {.constructor-modifier .features}
factory
:::

[Float64x2.zero](float64x2/float64x2.zero)()

::: {.constructor-modifier .features}
factory
:::

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[signMask](float64x2/signmask) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

Extract the sign bits from each lane return them in the first 2 bits.
\"x\" lane is bit 0. \"y\" lane is bit 1.

[x](float64x2/x) → [double](../dart-core/double-class)

::: {.features}
read-only
:::

Extracted x value.

[y](float64x2/y) → [double](../dart-core/double-class)

::: {.features}
read-only
:::

Extracted y value.

Methods {#instance-methods}
-------

[abs](float64x2/abs)() → [Float64x2](float64x2-class)

Returns the lane-wise absolute value of this
[Float64x2](float64x2-class).

[clamp](float64x2/clamp)([Float64x2](float64x2-class) lowerLimit,
[Float64x2](float64x2-class) upperLimit) → [Float64x2](float64x2-class)

Lane-wise clamp [this](float64x2-class) to be in the range
`lowerLimit`-`upperLimit`.

[max](float64x2/max)([Float64x2](float64x2-class) other) →
[Float64x2](float64x2-class)

Returns the lane-wise maximum value in [this](float64x2-class) or
`other`.

[min](float64x2/min)([Float64x2](float64x2-class) other) →
[Float64x2](float64x2-class)

Returns the lane-wise minimum value in [this](float64x2-class) or
`other`.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[scale](float64x2/scale)([double](../dart-core/double-class) s) →
[Float64x2](float64x2-class)

Returns a copy of [this](float64x2-class) each lane being scaled by `s`.
Equivalent to this \* new Float64x2.splat(s)

[sqrt](float64x2/sqrt)() → [Float64x2](float64x2-class)

Returns the lane-wise square root of [this](float64x2-class).

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

[withX](float64x2/withx)([double](../dart-core/double-class) x) →
[Float64x2](float64x2-class)

Returns a new [Float64x2](float64x2-class) copied from
[this](float64x2-class) with a new x value.

[withY](float64x2/withy)([double](../dart-core/double-class) y) →
[Float64x2](float64x2-class)

Returns a new [Float64x2](float64x2-class) copied from
[this](float64x2-class) with a new y value.

Operators
---------

[operator \*](float64x2/operator_multiply)([Float64x2](float64x2-class)
other) → [Float64x2](float64x2-class)

Multiplication operator.

[operator +](float64x2/operator_plus)([Float64x2](float64x2-class)
other) → [Float64x2](float64x2-class)

Addition operator.

[operator -](float64x2/operator_minus)([Float64x2](float64x2-class)
other) → [Float64x2](float64x2-class)

Subtraction operator.

[operator /](float64x2/operator_divide)([Float64x2](float64x2-class)
other) → [Float64x2](float64x2-class)

Division operator.

[operator
==](../dart-core/object/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

[operator unary-](float64x2/operator_unary_minus)() →
[Float64x2](float64x2-class)

Negate operator.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/Float64x2-class.html>
:::
