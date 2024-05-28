[dart:ffi](../dart-ffi/dart-ffi-library){._links-link}

UnsignedShort class
===================

The C `unsigned short` type.

Typically an unsigned 16-bit integer. For a guaranteed 16-bit integer,
use [Uint16](uint16-class) with the C `uint16_t` type. For a signed
`short`, use [Short](short-class).

The [UnsignedShort](unsignedshort-class) type is a native type, and
should not be constructed in Dart code. It occurs only in native type
signatures and as annotation on [Struct](struct-class) and
[Union](union-class) fields.

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [NativeType](nativetype-class)
    -   [AbiSpecificInteger](abispecificinteger-class)
    -   UnsignedShort

Annotations

:   -   \@Since(\'2.17\')
    -   @[AbiSpecificIntegerMapping](abispecificintegermapping-class)({Abi.androidArm
        : Uint16(), Abi.androidArm64 : Uint16(), Abi.androidIA32 :
        Uint16(), Abi.androidX64 : Uint16(), Abi.fuchsiaArm64 :
        Uint16(), Abi.fuchsiaX64 : Uint16(), Abi.iosArm : Uint16(),
        Abi.iosArm64 : Uint16(), Abi.iosX64 : Uint16(), Abi.linuxArm :
        Uint16(), Abi.linuxArm64 : Uint16(), Abi.linuxIA32 : Uint16(),
        Abi.linuxX64 : Uint16(), Abi.linuxRiscv32 : Uint16(),
        Abi.linuxRiscv64 : Uint16(), Abi.macosArm64 : Uint16(),
        Abi.macosX64 : Uint16(), Abi.windowsArm64 : Uint16(),
        Abi.windowsIA32 : Uint16(), Abi.windowsX64 : Uint16()})

Constructors
------------

[UnsignedShort](unsignedshort/unsignedshort)()

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
<https://api.dart.dev/stable/2.18.5/dart-ffi/UnsignedShort-class.html>
:::
