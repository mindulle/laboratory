[dart:ffi](../dart-ffi/dart-ffi-library){._links-link}

Short class
===========

The C `short` type.

Typically a signed 16-bit integer. For a guaranteed 16-bit integer, use
[Int16](int16-class) with the C `int16_t` type. For an `unsigned short`,
use [UnsignedShort](unsignedshort-class).

The [Short](short-class) type is a native type, and should not be
constructed in Dart code. It occurs only in native type signatures and
as annotation on [Struct](struct-class) and [Union](union-class) fields.

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [NativeType](nativetype-class)
    -   [AbiSpecificInteger](abispecificinteger-class)
    -   Short

Annotations

:   -   \@Since(\'2.17\')
    -   @[AbiSpecificIntegerMapping](abispecificintegermapping-class)({Abi.androidArm
        : Int16(), Abi.androidArm64 : Int16(), Abi.androidIA32 :
        Int16(), Abi.androidX64 : Int16(), Abi.fuchsiaArm64 : Int16(),
        Abi.fuchsiaX64 : Int16(), Abi.iosArm : Int16(), Abi.iosArm64 :
        Int16(), Abi.iosX64 : Int16(), Abi.linuxArm : Int16(),
        Abi.linuxArm64 : Int16(), Abi.linuxIA32 : Int16(), Abi.linuxX64
        : Int16(), Abi.linuxRiscv32 : Int16(), Abi.linuxRiscv64 :
        Int16(), Abi.macosArm64 : Int16(), Abi.macosX64 : Int16(),
        Abi.windowsArm64 : Int16(), Abi.windowsIA32 : Int16(),
        Abi.windowsX64 : Int16()})

Constructors
------------

[Short](short/short)()

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
<https://api.dart.dev/stable/2.18.5/dart-ffi/Short-class.html>
:::
