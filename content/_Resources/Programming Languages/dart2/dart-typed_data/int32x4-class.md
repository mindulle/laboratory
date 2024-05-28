[dart:typed\_data](../dart-typed_data/dart-typed_data-library){._links-link}

Int32x4 class
=============

Int32x4 and operations.

Int32x4 stores 4 32-bit bit-masks in \"lanes\". The lanes are \"x\",
\"y\", \"z\", and \"w\" respectively.

Constructors
------------

[Int32x4](int32x4/int32x4)([int](../dart-core/int-class) x,
[int](../dart-core/int-class) y, [int](../dart-core/int-class) z,
[int](../dart-core/int-class) w)

::: {.constructor-modifier .features}
factory
:::

[Int32x4.bool](int32x4/int32x4.bool)([bool](../dart-core/bool-class) x,
[bool](../dart-core/bool-class) y, [bool](../dart-core/bool-class) z,
[bool](../dart-core/bool-class) w)

::: {.constructor-modifier .features}
factory
:::

[Int32x4.fromFloat32x4Bits](int32x4/int32x4.fromfloat32x4bits)([Float32x4](float32x4-class)
x)

::: {.constructor-modifier .features}
factory
:::

Properties {#instance-properties}
----------

[flagW](int32x4/flagw) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Extracted w value. Returns false for 0, true for any other value.

[flagX](int32x4/flagx) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Extracted x value. Returns false for 0, true for any other value.

[flagY](int32x4/flagy) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Extracted y value. Returns false for 0, true for any other value.

[flagZ](int32x4/flagz) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Extracted z value. Returns false for 0, true for any other value.

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

[signMask](int32x4/signmask) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

Extract the top bit from each lane return them in the first 4 bits.
\"x\" lane is bit 0. \"y\" lane is bit 1. \"z\" lane is bit 2. \"w\"
lane is bit 3.

[w](int32x4/w) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

Extract 32-bit mask from w lane.

[x](int32x4/x) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

Extract 32-bit mask from x lane.

[y](int32x4/y) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

Extract 32-bit mask from y lane.

[z](int32x4/z) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

Extract 32-bit mask from z lane.

Methods {#instance-methods}
-------

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[select](int32x4/select)([Float32x4](float32x4-class) trueValue,
[Float32x4](float32x4-class) falseValue) → [Float32x4](float32x4-class)

Merge `trueValue` and `falseValue` based on [this](int32x4-class)\' bit
mask: Select bit from `trueValue` when bit in [this](int32x4-class) is
on. Select bit from `falseValue` when bit in [this](int32x4-class) is
off.

[shuffle](int32x4/shuffle)([int](../dart-core/int-class) mask) →
[Int32x4](int32x4-class)

Shuffle the lane values. `mask` must be one of the 256 shuffle
constants.

[shuffleMix](int32x4/shufflemix)([Int32x4](int32x4-class) other,
[int](../dart-core/int-class) mask) → [Int32x4](int32x4-class)

Shuffle the lane values in [this](int32x4-class) and `other`. The
returned Int32x4 will have XY lanes from [this](int32x4-class) and ZW
lanes from `other`. Uses the same `mask` as [shuffle](int32x4/shuffle).

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

[withFlagW](int32x4/withflagw)([bool](../dart-core/bool-class) w) →
[Int32x4](int32x4-class)

Returns a new [Int32x4](int32x4-class) copied from [this](int32x4-class)
with a new w value.

[withFlagX](int32x4/withflagx)([bool](../dart-core/bool-class) x) →
[Int32x4](int32x4-class)

Returns a new [Int32x4](int32x4-class) copied from [this](int32x4-class)
with a new x value.

[withFlagY](int32x4/withflagy)([bool](../dart-core/bool-class) y) →
[Int32x4](int32x4-class)

Returns a new [Int32x4](int32x4-class) copied from [this](int32x4-class)
with a new y value.

[withFlagZ](int32x4/withflagz)([bool](../dart-core/bool-class) z) →
[Int32x4](int32x4-class)

Returns a new [Int32x4](int32x4-class) copied from [this](int32x4-class)
with a new z value.

[withW](int32x4/withw)([int](../dart-core/int-class) w) →
[Int32x4](int32x4-class)

Returns a new [Int32x4](int32x4-class) copied from [this](int32x4-class)
with a new w value.

[withX](int32x4/withx)([int](../dart-core/int-class) x) →
[Int32x4](int32x4-class)

Returns a new [Int32x4](int32x4-class) copied from [this](int32x4-class)
with a new x value.

[withY](int32x4/withy)([int](../dart-core/int-class) y) →
[Int32x4](int32x4-class)

Returns a new [Int32x4](int32x4-class) copied from [this](int32x4-class)
with a new y value.

[withZ](int32x4/withz)([int](../dart-core/int-class) z) →
[Int32x4](int32x4-class)

Returns a new [Int32x4](int32x4-class) copied from [this](int32x4-class)
with a new z value.

Operators
---------

[operator &](int32x4/operator_bitwise_and)([Int32x4](int32x4-class)
other) → [Int32x4](int32x4-class)

The bit-wise and operator.

[operator +](int32x4/operator_plus)([Int32x4](int32x4-class) other) →
[Int32x4](int32x4-class)

Addition operator.

[operator -](int32x4/operator_minus)([Int32x4](int32x4-class) other) →
[Int32x4](int32x4-class)

Subtraction operator.

[operator
==](../dart-core/object/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

[operator
\^](int32x4/operator_bitwise_exclusive_or)([Int32x4](int32x4-class)
other) → [Int32x4](int32x4-class)

The bit-wise xor operator.

[operator \|](int32x4/operator_bitwise_or)([Int32x4](int32x4-class)
other) → [Int32x4](int32x4-class)

The bit-wise or operator.

Constants
---------

[wwww](int32x4/wwww-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xFF`

    </div>

[wwwx](int32x4/wwwx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x3F`

    </div>

[wwwy](int32x4/wwwy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x7F`

    </div>

[wwwz](int32x4/wwwz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xBF`

    </div>

[wwxw](int32x4/wwxw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xCF`

    </div>

[wwxx](int32x4/wwxx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xF`

    </div>

[wwxy](int32x4/wwxy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x4F`

    </div>

[wwxz](int32x4/wwxz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x8F`

    </div>

[wwyw](int32x4/wwyw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xDF`

    </div>

[wwyx](int32x4/wwyx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x1F`

    </div>

[wwyy](int32x4/wwyy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x5F`

    </div>

[wwyz](int32x4/wwyz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x9F`

    </div>

[wwzw](int32x4/wwzw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xEF`

    </div>

[wwzx](int32x4/wwzx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x2F`

    </div>

[wwzy](int32x4/wwzy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x6F`

    </div>

[wwzz](int32x4/wwzz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xAF`

    </div>

[wxww](int32x4/wxww-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xF3`

    </div>

[wxwx](int32x4/wxwx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x33`

    </div>

[wxwy](int32x4/wxwy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x73`

    </div>

[wxwz](int32x4/wxwz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xB3`

    </div>

[wxxw](int32x4/wxxw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xC3`

    </div>

[wxxx](int32x4/wxxx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x3`

    </div>

[wxxy](int32x4/wxxy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x43`

    </div>

[wxxz](int32x4/wxxz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x83`

    </div>

[wxyw](int32x4/wxyw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xD3`

    </div>

[wxyx](int32x4/wxyx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x13`

    </div>

[wxyy](int32x4/wxyy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x53`

    </div>

[wxyz](int32x4/wxyz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x93`

    </div>

[wxzw](int32x4/wxzw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xE3`

    </div>

[wxzx](int32x4/wxzx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x23`

    </div>

[wxzy](int32x4/wxzy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x63`

    </div>

[wxzz](int32x4/wxzz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xA3`

    </div>

[wyww](int32x4/wyww-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xF7`

    </div>

[wywx](int32x4/wywx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x37`

    </div>

[wywy](int32x4/wywy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x77`

    </div>

[wywz](int32x4/wywz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xB7`

    </div>

[wyxw](int32x4/wyxw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xC7`

    </div>

[wyxx](int32x4/wyxx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x7`

    </div>

[wyxy](int32x4/wyxy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x47`

    </div>

[wyxz](int32x4/wyxz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x87`

    </div>

[wyyw](int32x4/wyyw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xD7`

    </div>

[wyyx](int32x4/wyyx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x17`

    </div>

[wyyy](int32x4/wyyy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x57`

    </div>

[wyyz](int32x4/wyyz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x97`

    </div>

[wyzw](int32x4/wyzw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xE7`

    </div>

[wyzx](int32x4/wyzx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x27`

    </div>

[wyzy](int32x4/wyzy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x67`

    </div>

[wyzz](int32x4/wyzz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xA7`

    </div>

[wzww](int32x4/wzww-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xFB`

    </div>

[wzwx](int32x4/wzwx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x3B`

    </div>

[wzwy](int32x4/wzwy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x7B`

    </div>

[wzwz](int32x4/wzwz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xBB`

    </div>

[wzxw](int32x4/wzxw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xCB`

    </div>

[wzxx](int32x4/wzxx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xB`

    </div>

[wzxy](int32x4/wzxy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x4B`

    </div>

[wzxz](int32x4/wzxz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x8B`

    </div>

[wzyw](int32x4/wzyw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xDB`

    </div>

[wzyx](int32x4/wzyx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x1B`

    </div>

[wzyy](int32x4/wzyy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x5B`

    </div>

[wzyz](int32x4/wzyz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x9B`

    </div>

[wzzw](int32x4/wzzw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xEB`

    </div>

[wzzx](int32x4/wzzx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x2B`

    </div>

[wzzy](int32x4/wzzy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x6B`

    </div>

[wzzz](int32x4/wzzz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xAB`

    </div>

[xwww](int32x4/xwww-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xFC`

    </div>

[xwwx](int32x4/xwwx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x3C`

    </div>

[xwwy](int32x4/xwwy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x7C`

    </div>

[xwwz](int32x4/xwwz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xBC`

    </div>

[xwxw](int32x4/xwxw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xCC`

    </div>

[xwxx](int32x4/xwxx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xC`

    </div>

[xwxy](int32x4/xwxy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x4C`

    </div>

[xwxz](int32x4/xwxz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x8C`

    </div>

[xwyw](int32x4/xwyw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xDC`

    </div>

[xwyx](int32x4/xwyx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x1C`

    </div>

[xwyy](int32x4/xwyy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x5C`

    </div>

[xwyz](int32x4/xwyz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x9C`

    </div>

[xwzw](int32x4/xwzw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xEC`

    </div>

[xwzx](int32x4/xwzx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x2C`

    </div>

[xwzy](int32x4/xwzy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x6C`

    </div>

[xwzz](int32x4/xwzz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xAC`

    </div>

[xxww](int32x4/xxww-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xF0`

    </div>

[xxwx](int32x4/xxwx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x30`

    </div>

[xxwy](int32x4/xxwy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x70`

    </div>

[xxwz](int32x4/xxwz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xB0`

    </div>

[xxxw](int32x4/xxxw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xC0`

    </div>

[xxxx](int32x4/xxxx-constant) → const [int](../dart-core/int-class)
:   Mask passed to [shuffle](int32x4/shuffle) or
    [shuffleMix](int32x4/shufflemix).
    <div>

    `0x0`

    </div>

[xxxy](int32x4/xxxy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x40`

    </div>

[xxxz](int32x4/xxxz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x80`

    </div>

[xxyw](int32x4/xxyw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xD0`

    </div>

[xxyx](int32x4/xxyx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x10`

    </div>

[xxyy](int32x4/xxyy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x50`

    </div>

[xxyz](int32x4/xxyz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x90`

    </div>

[xxzw](int32x4/xxzw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xE0`

    </div>

[xxzx](int32x4/xxzx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x20`

    </div>

[xxzy](int32x4/xxzy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x60`

    </div>

[xxzz](int32x4/xxzz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xA0`

    </div>

[xyww](int32x4/xyww-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xF4`

    </div>

[xywx](int32x4/xywx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x34`

    </div>

[xywy](int32x4/xywy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x74`

    </div>

[xywz](int32x4/xywz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xB4`

    </div>

[xyxw](int32x4/xyxw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xC4`

    </div>

[xyxx](int32x4/xyxx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x4`

    </div>

[xyxy](int32x4/xyxy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x44`

    </div>

[xyxz](int32x4/xyxz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x84`

    </div>

[xyyw](int32x4/xyyw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xD4`

    </div>

[xyyx](int32x4/xyyx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x14`

    </div>

[xyyy](int32x4/xyyy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x54`

    </div>

[xyyz](int32x4/xyyz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x94`

    </div>

[xyzw](int32x4/xyzw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xE4`

    </div>

[xyzx](int32x4/xyzx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x24`

    </div>

[xyzy](int32x4/xyzy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x64`

    </div>

[xyzz](int32x4/xyzz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xA4`

    </div>

[xzww](int32x4/xzww-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xF8`

    </div>

[xzwx](int32x4/xzwx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x38`

    </div>

[xzwy](int32x4/xzwy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x78`

    </div>

[xzwz](int32x4/xzwz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xB8`

    </div>

[xzxw](int32x4/xzxw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xC8`

    </div>

[xzxx](int32x4/xzxx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x8`

    </div>

[xzxy](int32x4/xzxy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x48`

    </div>

[xzxz](int32x4/xzxz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x88`

    </div>

[xzyw](int32x4/xzyw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xD8`

    </div>

[xzyx](int32x4/xzyx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x18`

    </div>

[xzyy](int32x4/xzyy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x58`

    </div>

[xzyz](int32x4/xzyz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x98`

    </div>

[xzzw](int32x4/xzzw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xE8`

    </div>

[xzzx](int32x4/xzzx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x28`

    </div>

[xzzy](int32x4/xzzy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x68`

    </div>

[xzzz](int32x4/xzzz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xA8`

    </div>

[ywww](int32x4/ywww-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xFD`

    </div>

[ywwx](int32x4/ywwx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x3D`

    </div>

[ywwy](int32x4/ywwy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x7D`

    </div>

[ywwz](int32x4/ywwz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xBD`

    </div>

[ywxw](int32x4/ywxw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xCD`

    </div>

[ywxx](int32x4/ywxx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xD`

    </div>

[ywxy](int32x4/ywxy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x4D`

    </div>

[ywxz](int32x4/ywxz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x8D`

    </div>

[ywyw](int32x4/ywyw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xDD`

    </div>

[ywyx](int32x4/ywyx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x1D`

    </div>

[ywyy](int32x4/ywyy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x5D`

    </div>

[ywyz](int32x4/ywyz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x9D`

    </div>

[ywzw](int32x4/ywzw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xED`

    </div>

[ywzx](int32x4/ywzx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x2D`

    </div>

[ywzy](int32x4/ywzy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x6D`

    </div>

[ywzz](int32x4/ywzz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xAD`

    </div>

[yxww](int32x4/yxww-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xF1`

    </div>

[yxwx](int32x4/yxwx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x31`

    </div>

[yxwy](int32x4/yxwy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x71`

    </div>

[yxwz](int32x4/yxwz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xB1`

    </div>

[yxxw](int32x4/yxxw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xC1`

    </div>

[yxxx](int32x4/yxxx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x1`

    </div>

[yxxy](int32x4/yxxy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x41`

    </div>

[yxxz](int32x4/yxxz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x81`

    </div>

[yxyw](int32x4/yxyw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xD1`

    </div>

[yxyx](int32x4/yxyx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x11`

    </div>

[yxyy](int32x4/yxyy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x51`

    </div>

[yxyz](int32x4/yxyz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x91`

    </div>

[yxzw](int32x4/yxzw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xE1`

    </div>

[yxzx](int32x4/yxzx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x21`

    </div>

[yxzy](int32x4/yxzy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x61`

    </div>

[yxzz](int32x4/yxzz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xA1`

    </div>

[yyww](int32x4/yyww-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xF5`

    </div>

[yywx](int32x4/yywx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x35`

    </div>

[yywy](int32x4/yywy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x75`

    </div>

[yywz](int32x4/yywz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xB5`

    </div>

[yyxw](int32x4/yyxw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xC5`

    </div>

[yyxx](int32x4/yyxx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x5`

    </div>

[yyxy](int32x4/yyxy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x45`

    </div>

[yyxz](int32x4/yyxz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x85`

    </div>

[yyyw](int32x4/yyyw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xD5`

    </div>

[yyyx](int32x4/yyyx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x15`

    </div>

[yyyy](int32x4/yyyy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x55`

    </div>

[yyyz](int32x4/yyyz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x95`

    </div>

[yyzw](int32x4/yyzw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xE5`

    </div>

[yyzx](int32x4/yyzx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x25`

    </div>

[yyzy](int32x4/yyzy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x65`

    </div>

[yyzz](int32x4/yyzz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xA5`

    </div>

[yzww](int32x4/yzww-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xF9`

    </div>

[yzwx](int32x4/yzwx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x39`

    </div>

[yzwy](int32x4/yzwy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x79`

    </div>

[yzwz](int32x4/yzwz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xB9`

    </div>

[yzxw](int32x4/yzxw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xC9`

    </div>

[yzxx](int32x4/yzxx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x9`

    </div>

[yzxy](int32x4/yzxy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x49`

    </div>

[yzxz](int32x4/yzxz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x89`

    </div>

[yzyw](int32x4/yzyw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xD9`

    </div>

[yzyx](int32x4/yzyx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x19`

    </div>

[yzyy](int32x4/yzyy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x59`

    </div>

[yzyz](int32x4/yzyz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x99`

    </div>

[yzzw](int32x4/yzzw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xE9`

    </div>

[yzzx](int32x4/yzzx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x29`

    </div>

[yzzy](int32x4/yzzy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x69`

    </div>

[yzzz](int32x4/yzzz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xA9`

    </div>

[zwww](int32x4/zwww-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xFE`

    </div>

[zwwx](int32x4/zwwx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x3E`

    </div>

[zwwy](int32x4/zwwy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x7E`

    </div>

[zwwz](int32x4/zwwz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xBE`

    </div>

[zwxw](int32x4/zwxw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xCE`

    </div>

[zwxx](int32x4/zwxx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xE`

    </div>

[zwxy](int32x4/zwxy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x4E`

    </div>

[zwxz](int32x4/zwxz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x8E`

    </div>

[zwyw](int32x4/zwyw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xDE`

    </div>

[zwyx](int32x4/zwyx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x1E`

    </div>

[zwyy](int32x4/zwyy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x5E`

    </div>

[zwyz](int32x4/zwyz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x9E`

    </div>

[zwzw](int32x4/zwzw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xEE`

    </div>

[zwzx](int32x4/zwzx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x2E`

    </div>

[zwzy](int32x4/zwzy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x6E`

    </div>

[zwzz](int32x4/zwzz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xAE`

    </div>

[zxww](int32x4/zxww-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xF2`

    </div>

[zxwx](int32x4/zxwx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x32`

    </div>

[zxwy](int32x4/zxwy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x72`

    </div>

[zxwz](int32x4/zxwz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xB2`

    </div>

[zxxw](int32x4/zxxw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xC2`

    </div>

[zxxx](int32x4/zxxx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x2`

    </div>

[zxxy](int32x4/zxxy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x42`

    </div>

[zxxz](int32x4/zxxz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x82`

    </div>

[zxyw](int32x4/zxyw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xD2`

    </div>

[zxyx](int32x4/zxyx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x12`

    </div>

[zxyy](int32x4/zxyy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x52`

    </div>

[zxyz](int32x4/zxyz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x92`

    </div>

[zxzw](int32x4/zxzw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xE2`

    </div>

[zxzx](int32x4/zxzx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x22`

    </div>

[zxzy](int32x4/zxzy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x62`

    </div>

[zxzz](int32x4/zxzz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xA2`

    </div>

[zyww](int32x4/zyww-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xF6`

    </div>

[zywx](int32x4/zywx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x36`

    </div>

[zywy](int32x4/zywy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x76`

    </div>

[zywz](int32x4/zywz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xB6`

    </div>

[zyxw](int32x4/zyxw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xC6`

    </div>

[zyxx](int32x4/zyxx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x6`

    </div>

[zyxy](int32x4/zyxy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x46`

    </div>

[zyxz](int32x4/zyxz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x86`

    </div>

[zyyw](int32x4/zyyw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xD6`

    </div>

[zyyx](int32x4/zyyx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x16`

    </div>

[zyyy](int32x4/zyyy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x56`

    </div>

[zyyz](int32x4/zyyz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x96`

    </div>

[zyzw](int32x4/zyzw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xE6`

    </div>

[zyzx](int32x4/zyzx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x26`

    </div>

[zyzy](int32x4/zyzy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x66`

    </div>

[zyzz](int32x4/zyzz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xA6`

    </div>

[zzww](int32x4/zzww-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xFA`

    </div>

[zzwx](int32x4/zzwx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x3A`

    </div>

[zzwy](int32x4/zzwy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x7A`

    </div>

[zzwz](int32x4/zzwz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xBA`

    </div>

[zzxw](int32x4/zzxw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xCA`

    </div>

[zzxx](int32x4/zzxx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xA`

    </div>

[zzxy](int32x4/zzxy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x4A`

    </div>

[zzxz](int32x4/zzxz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x8A`

    </div>

[zzyw](int32x4/zzyw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xDA`

    </div>

[zzyx](int32x4/zzyx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x1A`

    </div>

[zzyy](int32x4/zzyy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x5A`

    </div>

[zzyz](int32x4/zzyz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x9A`

    </div>

[zzzw](int32x4/zzzw-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xEA`

    </div>

[zzzx](int32x4/zzzx-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x2A`

    </div>

[zzzy](int32x4/zzzy-constant) → const [int](../dart-core/int-class)

:   <div>

    `0x6A`

    </div>

[zzzz](int32x4/zzzz-constant) → const [int](../dart-core/int-class)

:   <div>

    `0xAA`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/Int32x4-class.html>
:::
