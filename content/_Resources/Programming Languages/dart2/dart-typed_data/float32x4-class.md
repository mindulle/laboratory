[dart:typed\_data](../dart-typed_data/dart-typed_data-library){._links-link}

Float32x4 class
===============

Float32x4 immutable value type and operations.

Float32x4 stores 4 32-bit floating point values in \"lanes\". The lanes
are \"x\", \"y\", \"z\", and \"w\" respectively.

Constructors
------------

[Float32x4](float32x4/float32x4)([double](../dart-core/double-class) x,
[double](../dart-core/double-class) y,
[double](../dart-core/double-class) z,
[double](../dart-core/double-class) w)

::: {.constructor-modifier .features}
factory
:::

[Float32x4.fromFloat64x2](float32x4/float32x4.fromfloat64x2)([Float64x2](float64x2-class)
v)

::: {.constructor-modifier .features}
factory
:::

Sets the x and y lanes to their respective values in `v` and sets the z
and w lanes to 0.0.

[Float32x4.fromInt32x4Bits](float32x4/float32x4.fromint32x4bits)([Int32x4](int32x4-class)
x)

::: {.constructor-modifier .features}
factory
:::

[Float32x4.splat](float32x4/float32x4.splat)([double](../dart-core/double-class)
v)

::: {.constructor-modifier .features}
factory
:::

[Float32x4.zero](float32x4/float32x4.zero)()

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

[signMask](float32x4/signmask) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

Extract the sign bits from each lane return them in the first 4 bits.
\"x\" lane is bit 0. \"y\" lane is bit 1. \"z\" lane is bit 2. \"w\"
lane is bit 3.

[w](float32x4/w) → [double](../dart-core/double-class)

::: {.features}
read-only
:::

Extracted w value.

[x](float32x4/x) → [double](../dart-core/double-class)

::: {.features}
read-only
:::

Extracted x value.

[y](float32x4/y) → [double](../dart-core/double-class)

::: {.features}
read-only
:::

Extracted y value.

[z](float32x4/z) → [double](../dart-core/double-class)

::: {.features}
read-only
:::

Extracted z value.

Methods {#instance-methods}
-------

[abs](float32x4/abs)() → [Float32x4](float32x4-class)

Returns the lane-wise absolute value of this
[Float32x4](float32x4-class).

[clamp](float32x4/clamp)([Float32x4](float32x4-class) lowerLimit,
[Float32x4](float32x4-class) upperLimit) → [Float32x4](float32x4-class)

Lane-wise clamp [this](float32x4-class) to be in the range
`lowerLimit`-`upperLimit`.

[equal](float32x4/equal)([Float32x4](float32x4-class) other) →
[Int32x4](int32x4-class)

Relational equal.

[greaterThan](float32x4/greaterthan)([Float32x4](float32x4-class) other)
→ [Int32x4](int32x4-class)

Relational greater than.

[greaterThanOrEqual](float32x4/greaterthanorequal)([Float32x4](float32x4-class)
other) → [Int32x4](int32x4-class)

Relational greater than or equal.

[lessThan](float32x4/lessthan)([Float32x4](float32x4-class) other) →
[Int32x4](int32x4-class)

Relational less than.

[lessThanOrEqual](float32x4/lessthanorequal)([Float32x4](float32x4-class)
other) → [Int32x4](int32x4-class)

Relational less than or equal.

[max](float32x4/max)([Float32x4](float32x4-class) other) →
[Float32x4](float32x4-class)

Returns the lane-wise maximum value in [this](float32x4-class) or
`other`.

[min](float32x4/min)([Float32x4](float32x4-class) other) →
[Float32x4](float32x4-class)

Returns the lane-wise minimum value in [this](float32x4-class) or
`other`.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[notEqual](float32x4/notequal)([Float32x4](float32x4-class) other) →
[Int32x4](int32x4-class)

Relational not-equal.

[reciprocal](float32x4/reciprocal)() → [Float32x4](float32x4-class)

Returns the reciprocal of [this](float32x4-class).

[reciprocalSqrt](float32x4/reciprocalsqrt)() →
[Float32x4](float32x4-class)

Returns the square root of the reciprocal of [this](float32x4-class).

[scale](float32x4/scale)([double](../dart-core/double-class) s) →
[Float32x4](float32x4-class)

Returns a copy of [this](float32x4-class) each lane being scaled by `s`.
Equivalent to this \* new Float32x4.splat(s)

[shuffle](float32x4/shuffle)([int](../dart-core/int-class) mask) →
[Float32x4](float32x4-class)

Shuffle the lane values. `mask` must be one of the 256 shuffle
constants.

[shuffleMix](float32x4/shufflemix)([Float32x4](float32x4-class) other,
[int](../dart-core/int-class) mask) → [Float32x4](float32x4-class)

Shuffle the lane values in [this](float32x4-class) and `other`. The
returned Float32x4 will have XY lanes from [this](float32x4-class) and
ZW lanes from `other`. Uses the same `mask` as
[shuffle](float32x4/shuffle).

[sqrt](float32x4/sqrt)() → [Float32x4](float32x4-class)

Returns the square root of [this](float32x4-class).

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

[withW](float32x4/withw)([double](../dart-core/double-class) w) →
[Float32x4](float32x4-class)

Returns a new [Float32x4](float32x4-class) copied from
[this](float32x4-class) with a new w value.

[withX](float32x4/withx)([double](../dart-core/double-class) x) →
[Float32x4](float32x4-class)

Returns a new [Float32x4](float32x4-class) copied from
[this](float32x4-class) with a new x value.

[withY](float32x4/withy)([double](../dart-core/double-class) y) →
[Float32x4](float32x4-class)

Returns a new [Float32x4](float32x4-class) copied from
[this](float32x4-class) with a new y value.

[withZ](float32x4/withz)([double](../dart-core/double-class) z) →
[Float32x4](float32x4-class)

Returns a new [Float32x4](float32x4-class) copied from
[this](float32x4-class) with a new z value.

Operators
---------

[operator \*](float32x4/operator_multiply)([Float32x4](float32x4-class)
other) → [Float32x4](float32x4-class)

Multiplication operator.

[operator +](float32x4/operator_plus)([Float32x4](float32x4-class)
other) → [Float32x4](float32x4-class)

Addition operator.

[operator -](float32x4/operator_minus)([Float32x4](float32x4-class)
other) → [Float32x4](float32x4-class)

Subtraction operator.

[operator /](float32x4/operator_divide)([Float32x4](float32x4-class)
other) → [Float32x4](float32x4-class)

Division operator.

[operator
==](../dart-core/object/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

[operator unary-](float32x4/operator_unary_minus)() →
[Float32x4](float32x4-class)

Negate operator.

Constants
---------

[wwww](float32x4/wwww-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xFF`

    </div>

[wwwx](float32x4/wwwx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x3F`

    </div>

[wwwy](float32x4/wwwy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x7F`

    </div>

[wwwz](float32x4/wwwz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xBF`

    </div>

[wwxw](float32x4/wwxw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xCF`

    </div>

[wwxx](float32x4/wwxx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xF`

    </div>

[wwxy](float32x4/wwxy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x4F`

    </div>

[wwxz](float32x4/wwxz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x8F`

    </div>

[wwyw](float32x4/wwyw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xDF`

    </div>

[wwyx](float32x4/wwyx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x1F`

    </div>

[wwyy](float32x4/wwyy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x5F`

    </div>

[wwyz](float32x4/wwyz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x9F`

    </div>

[wwzw](float32x4/wwzw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xEF`

    </div>

[wwzx](float32x4/wwzx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x2F`

    </div>

[wwzy](float32x4/wwzy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x6F`

    </div>

[wwzz](float32x4/wwzz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xAF`

    </div>

[wxww](float32x4/wxww-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xF3`

    </div>

[wxwx](float32x4/wxwx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x33`

    </div>

[wxwy](float32x4/wxwy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x73`

    </div>

[wxwz](float32x4/wxwz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xB3`

    </div>

[wxxw](float32x4/wxxw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xC3`

    </div>

[wxxx](float32x4/wxxx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x3`

    </div>

[wxxy](float32x4/wxxy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x43`

    </div>

[wxxz](float32x4/wxxz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x83`

    </div>

[wxyw](float32x4/wxyw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xD3`

    </div>

[wxyx](float32x4/wxyx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x13`

    </div>

[wxyy](float32x4/wxyy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x53`

    </div>

[wxyz](float32x4/wxyz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x93`

    </div>

[wxzw](float32x4/wxzw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xE3`

    </div>

[wxzx](float32x4/wxzx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x23`

    </div>

[wxzy](float32x4/wxzy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x63`

    </div>

[wxzz](float32x4/wxzz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xA3`

    </div>

[wyww](float32x4/wyww-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xF7`

    </div>

[wywx](float32x4/wywx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x37`

    </div>

[wywy](float32x4/wywy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x77`

    </div>

[wywz](float32x4/wywz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xB7`

    </div>

[wyxw](float32x4/wyxw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xC7`

    </div>

[wyxx](float32x4/wyxx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x7`

    </div>

[wyxy](float32x4/wyxy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x47`

    </div>

[wyxz](float32x4/wyxz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x87`

    </div>

[wyyw](float32x4/wyyw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xD7`

    </div>

[wyyx](float32x4/wyyx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x17`

    </div>

[wyyy](float32x4/wyyy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x57`

    </div>

[wyyz](float32x4/wyyz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x97`

    </div>

[wyzw](float32x4/wyzw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xE7`

    </div>

[wyzx](float32x4/wyzx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x27`

    </div>

[wyzy](float32x4/wyzy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x67`

    </div>

[wyzz](float32x4/wyzz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xA7`

    </div>

[wzww](float32x4/wzww-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xFB`

    </div>

[wzwx](float32x4/wzwx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x3B`

    </div>

[wzwy](float32x4/wzwy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x7B`

    </div>

[wzwz](float32x4/wzwz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xBB`

    </div>

[wzxw](float32x4/wzxw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xCB`

    </div>

[wzxx](float32x4/wzxx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xB`

    </div>

[wzxy](float32x4/wzxy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x4B`

    </div>

[wzxz](float32x4/wzxz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x8B`

    </div>

[wzyw](float32x4/wzyw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xDB`

    </div>

[wzyx](float32x4/wzyx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x1B`

    </div>

[wzyy](float32x4/wzyy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x5B`

    </div>

[wzyz](float32x4/wzyz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x9B`

    </div>

[wzzw](float32x4/wzzw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xEB`

    </div>

[wzzx](float32x4/wzzx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x2B`

    </div>

[wzzy](float32x4/wzzy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x6B`

    </div>

[wzzz](float32x4/wzzz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xAB`

    </div>

[xwww](float32x4/xwww-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xFC`

    </div>

[xwwx](float32x4/xwwx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x3C`

    </div>

[xwwy](float32x4/xwwy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x7C`

    </div>

[xwwz](float32x4/xwwz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xBC`

    </div>

[xwxw](float32x4/xwxw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xCC`

    </div>

[xwxx](float32x4/xwxx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xC`

    </div>

[xwxy](float32x4/xwxy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x4C`

    </div>

[xwxz](float32x4/xwxz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x8C`

    </div>

[xwyw](float32x4/xwyw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xDC`

    </div>

[xwyx](float32x4/xwyx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x1C`

    </div>

[xwyy](float32x4/xwyy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x5C`

    </div>

[xwyz](float32x4/xwyz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x9C`

    </div>

[xwzw](float32x4/xwzw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xEC`

    </div>

[xwzx](float32x4/xwzx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x2C`

    </div>

[xwzy](float32x4/xwzy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x6C`

    </div>

[xwzz](float32x4/xwzz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xAC`

    </div>

[xxww](float32x4/xxww-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xF0`

    </div>

[xxwx](float32x4/xxwx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x30`

    </div>

[xxwy](float32x4/xxwy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x70`

    </div>

[xxwz](float32x4/xxwz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xB0`

    </div>

[xxxw](float32x4/xxxw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xC0`

    </div>

[xxxx](float32x4/xxxx-constant) → const [int](../dart-core/int-class)
:   Mask passed to [shuffle](float32x4/shuffle) or
    [shuffleMix](float32x4/shufflemix).
    <div>

    `0x0`

    </div>

[xxxy](float32x4/xxxy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x40`

    </div>

[xxxz](float32x4/xxxz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x80`

    </div>

[xxyw](float32x4/xxyw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xD0`

    </div>

[xxyx](float32x4/xxyx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x10`

    </div>

[xxyy](float32x4/xxyy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x50`

    </div>

[xxyz](float32x4/xxyz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x90`

    </div>

[xxzw](float32x4/xxzw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xE0`

    </div>

[xxzx](float32x4/xxzx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x20`

    </div>

[xxzy](float32x4/xxzy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x60`

    </div>

[xxzz](float32x4/xxzz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xA0`

    </div>

[xyww](float32x4/xyww-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xF4`

    </div>

[xywx](float32x4/xywx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x34`

    </div>

[xywy](float32x4/xywy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x74`

    </div>

[xywz](float32x4/xywz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xB4`

    </div>

[xyxw](float32x4/xyxw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xC4`

    </div>

[xyxx](float32x4/xyxx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x4`

    </div>

[xyxy](float32x4/xyxy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x44`

    </div>

[xyxz](float32x4/xyxz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x84`

    </div>

[xyyw](float32x4/xyyw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xD4`

    </div>

[xyyx](float32x4/xyyx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x14`

    </div>

[xyyy](float32x4/xyyy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x54`

    </div>

[xyyz](float32x4/xyyz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x94`

    </div>

[xyzw](float32x4/xyzw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xE4`

    </div>

[xyzx](float32x4/xyzx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x24`

    </div>

[xyzy](float32x4/xyzy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x64`

    </div>

[xyzz](float32x4/xyzz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xA4`

    </div>

[xzww](float32x4/xzww-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xF8`

    </div>

[xzwx](float32x4/xzwx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x38`

    </div>

[xzwy](float32x4/xzwy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x78`

    </div>

[xzwz](float32x4/xzwz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xB8`

    </div>

[xzxw](float32x4/xzxw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xC8`

    </div>

[xzxx](float32x4/xzxx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x8`

    </div>

[xzxy](float32x4/xzxy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x48`

    </div>

[xzxz](float32x4/xzxz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x88`

    </div>

[xzyw](float32x4/xzyw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xD8`

    </div>

[xzyx](float32x4/xzyx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x18`

    </div>

[xzyy](float32x4/xzyy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x58`

    </div>

[xzyz](float32x4/xzyz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x98`

    </div>

[xzzw](float32x4/xzzw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xE8`

    </div>

[xzzx](float32x4/xzzx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x28`

    </div>

[xzzy](float32x4/xzzy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x68`

    </div>

[xzzz](float32x4/xzzz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xA8`

    </div>

[ywww](float32x4/ywww-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xFD`

    </div>

[ywwx](float32x4/ywwx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x3D`

    </div>

[ywwy](float32x4/ywwy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x7D`

    </div>

[ywwz](float32x4/ywwz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xBD`

    </div>

[ywxw](float32x4/ywxw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xCD`

    </div>

[ywxx](float32x4/ywxx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xD`

    </div>

[ywxy](float32x4/ywxy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x4D`

    </div>

[ywxz](float32x4/ywxz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x8D`

    </div>

[ywyw](float32x4/ywyw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xDD`

    </div>

[ywyx](float32x4/ywyx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x1D`

    </div>

[ywyy](float32x4/ywyy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x5D`

    </div>

[ywyz](float32x4/ywyz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x9D`

    </div>

[ywzw](float32x4/ywzw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xED`

    </div>

[ywzx](float32x4/ywzx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x2D`

    </div>

[ywzy](float32x4/ywzy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x6D`

    </div>

[ywzz](float32x4/ywzz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xAD`

    </div>

[yxww](float32x4/yxww-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xF1`

    </div>

[yxwx](float32x4/yxwx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x31`

    </div>

[yxwy](float32x4/yxwy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x71`

    </div>

[yxwz](float32x4/yxwz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xB1`

    </div>

[yxxw](float32x4/yxxw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xC1`

    </div>

[yxxx](float32x4/yxxx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x1`

    </div>

[yxxy](float32x4/yxxy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x41`

    </div>

[yxxz](float32x4/yxxz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x81`

    </div>

[yxyw](float32x4/yxyw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xD1`

    </div>

[yxyx](float32x4/yxyx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x11`

    </div>

[yxyy](float32x4/yxyy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x51`

    </div>

[yxyz](float32x4/yxyz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x91`

    </div>

[yxzw](float32x4/yxzw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xE1`

    </div>

[yxzx](float32x4/yxzx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x21`

    </div>

[yxzy](float32x4/yxzy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x61`

    </div>

[yxzz](float32x4/yxzz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xA1`

    </div>

[yyww](float32x4/yyww-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xF5`

    </div>

[yywx](float32x4/yywx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x35`

    </div>

[yywy](float32x4/yywy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x75`

    </div>

[yywz](float32x4/yywz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xB5`

    </div>

[yyxw](float32x4/yyxw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xC5`

    </div>

[yyxx](float32x4/yyxx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x5`

    </div>

[yyxy](float32x4/yyxy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x45`

    </div>

[yyxz](float32x4/yyxz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x85`

    </div>

[yyyw](float32x4/yyyw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xD5`

    </div>

[yyyx](float32x4/yyyx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x15`

    </div>

[yyyy](float32x4/yyyy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x55`

    </div>

[yyyz](float32x4/yyyz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x95`

    </div>

[yyzw](float32x4/yyzw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xE5`

    </div>

[yyzx](float32x4/yyzx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x25`

    </div>

[yyzy](float32x4/yyzy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x65`

    </div>

[yyzz](float32x4/yyzz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xA5`

    </div>

[yzww](float32x4/yzww-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xF9`

    </div>

[yzwx](float32x4/yzwx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x39`

    </div>

[yzwy](float32x4/yzwy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x79`

    </div>

[yzwz](float32x4/yzwz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xB9`

    </div>

[yzxw](float32x4/yzxw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xC9`

    </div>

[yzxx](float32x4/yzxx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x9`

    </div>

[yzxy](float32x4/yzxy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x49`

    </div>

[yzxz](float32x4/yzxz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x89`

    </div>

[yzyw](float32x4/yzyw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xD9`

    </div>

[yzyx](float32x4/yzyx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x19`

    </div>

[yzyy](float32x4/yzyy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x59`

    </div>

[yzyz](float32x4/yzyz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x99`

    </div>

[yzzw](float32x4/yzzw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xE9`

    </div>

[yzzx](float32x4/yzzx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x29`

    </div>

[yzzy](float32x4/yzzy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x69`

    </div>

[yzzz](float32x4/yzzz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xA9`

    </div>

[zwww](float32x4/zwww-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xFE`

    </div>

[zwwx](float32x4/zwwx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x3E`

    </div>

[zwwy](float32x4/zwwy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x7E`

    </div>

[zwwz](float32x4/zwwz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xBE`

    </div>

[zwxw](float32x4/zwxw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xCE`

    </div>

[zwxx](float32x4/zwxx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xE`

    </div>

[zwxy](float32x4/zwxy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x4E`

    </div>

[zwxz](float32x4/zwxz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x8E`

    </div>

[zwyw](float32x4/zwyw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xDE`

    </div>

[zwyx](float32x4/zwyx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x1E`

    </div>

[zwyy](float32x4/zwyy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x5E`

    </div>

[zwyz](float32x4/zwyz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x9E`

    </div>

[zwzw](float32x4/zwzw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xEE`

    </div>

[zwzx](float32x4/zwzx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x2E`

    </div>

[zwzy](float32x4/zwzy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x6E`

    </div>

[zwzz](float32x4/zwzz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xAE`

    </div>

[zxww](float32x4/zxww-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xF2`

    </div>

[zxwx](float32x4/zxwx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x32`

    </div>

[zxwy](float32x4/zxwy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x72`

    </div>

[zxwz](float32x4/zxwz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xB2`

    </div>

[zxxw](float32x4/zxxw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xC2`

    </div>

[zxxx](float32x4/zxxx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x2`

    </div>

[zxxy](float32x4/zxxy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x42`

    </div>

[zxxz](float32x4/zxxz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x82`

    </div>

[zxyw](float32x4/zxyw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xD2`

    </div>

[zxyx](float32x4/zxyx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x12`

    </div>

[zxyy](float32x4/zxyy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x52`

    </div>

[zxyz](float32x4/zxyz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x92`

    </div>

[zxzw](float32x4/zxzw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xE2`

    </div>

[zxzx](float32x4/zxzx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x22`

    </div>

[zxzy](float32x4/zxzy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x62`

    </div>

[zxzz](float32x4/zxzz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xA2`

    </div>

[zyww](float32x4/zyww-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xF6`

    </div>

[zywx](float32x4/zywx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x36`

    </div>

[zywy](float32x4/zywy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x76`

    </div>

[zywz](float32x4/zywz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xB6`

    </div>

[zyxw](float32x4/zyxw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xC6`

    </div>

[zyxx](float32x4/zyxx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x6`

    </div>

[zyxy](float32x4/zyxy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x46`

    </div>

[zyxz](float32x4/zyxz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x86`

    </div>

[zyyw](float32x4/zyyw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xD6`

    </div>

[zyyx](float32x4/zyyx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x16`

    </div>

[zyyy](float32x4/zyyy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x56`

    </div>

[zyyz](float32x4/zyyz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x96`

    </div>

[zyzw](float32x4/zyzw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xE6`

    </div>

[zyzx](float32x4/zyzx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x26`

    </div>

[zyzy](float32x4/zyzy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x66`

    </div>

[zyzz](float32x4/zyzz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xA6`

    </div>

[zzww](float32x4/zzww-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xFA`

    </div>

[zzwx](float32x4/zzwx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x3A`

    </div>

[zzwy](float32x4/zzwy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x7A`

    </div>

[zzwz](float32x4/zzwz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xBA`

    </div>

[zzxw](float32x4/zzxw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xCA`

    </div>

[zzxx](float32x4/zzxx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xA`

    </div>

[zzxy](float32x4/zzxy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x4A`

    </div>

[zzxz](float32x4/zzxz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x8A`

    </div>

[zzyw](float32x4/zzyw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xDA`

    </div>

[zzyx](float32x4/zzyx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x1A`

    </div>

[zzyy](float32x4/zzyy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x5A`

    </div>

[zzyz](float32x4/zzyz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x9A`

    </div>

[zzzw](float32x4/zzzw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xEA`

    </div>

[zzzx](float32x4/zzzx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x2A`

    </div>

[zzzy](float32x4/zzzy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x6A`

    </div>

[zzzz](float32x4/zzzz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xAA`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/Float32x4-class.html>
:::
