[dart:ffi](../dart-ffi/dart-ffi-library){._links-link}

Long class
==========

The C `long int`, aka. `long`, type.

Typically a signed 32- or 64-bit integer. For a guaranteed 32-bit
integer, use [Int32](int32-class) with the C `int32_t` type. For a
guaranteed 64-bit integer, use [Int64](int64-class) with the C `int64_t`
type. For an `unsigned long`, use [UnsignedLong](unsignedlong-class).

The [Long](long-class) type is a native type, and should not be
constructed in Dart code. It occurs only in native type signatures and
as annotation on [Struct](struct-class) and [Union](union-class) fields.

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [NativeType](nativetype-class)
    -   [AbiSpecificInteger](abispecificinteger-class)
    -   Long

Annotations

:   -   \@Since(\'2.17\')
    -   @[AbiSpecificIntegerMapping](abispecificintegermapping-class)({Abi.androidArm
        : Int32(), Abi.androidArm64 : Int64(), Abi.androidIA32 :
        Int32(), Abi.androidX64 : Int64(), Abi.fuchsiaArm64 : Int64(),
        Abi.fuchsiaX64 : Int64(), Abi.iosArm : Int32(), Abi.iosArm64 :
        Int64(), Abi.iosX64 : Int64(), Abi.linuxArm : Int32(),
        Abi.linuxArm64 : Int64(), Abi.linuxIA32 : Int32(), Abi.linuxX64
        : Int64(), Abi.linuxRiscv32 : Int32(), Abi.linuxRiscv64 :
        Int64(), Abi.macosArm64 : Int64(), Abi.macosX64 : Int64(),
        Abi.windowsArm64 : Int32(), Abi.windowsIA32 : Int32(),
        Abi.windowsX64 : Int32()})

Constructors
------------

[Long](long/long)()

::: {.constructor-modifier .features}
const
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

Methods {#instance-methods}
-------

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

Operators
---------

[operator
==](../dart-core/object/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/Long-class.html>
:::
