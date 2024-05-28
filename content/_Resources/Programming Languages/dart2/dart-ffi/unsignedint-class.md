[dart:ffi](../dart-ffi/dart-ffi-library){._links-link}

UnsignedInt class
=================

The C `unsigned int` type.

Typically an unsigned 32-bit integer. For a guaranteed 32-bit integer,
use [Uint32](uint32-class) with the C `uint32_t` type. For a signed
`int`, use [Int](int-class).

The [UnsignedInt](unsignedint-class) type is a native type, and should
not be constructed in Dart code. It occurs only in native type
signatures and as annotation on [Struct](struct-class) and
[Union](union-class) fields.

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [NativeType](nativetype-class)
    -   [AbiSpecificInteger](abispecificinteger-class)
    -   UnsignedInt

Annotations

:   -   \@Since(\'2.17\')
    -   @[AbiSpecificIntegerMapping](abispecificintegermapping-class)({Abi.androidArm
        : Uint32(), Abi.androidArm64 : Uint32(), Abi.androidIA32 :
        Uint32(), Abi.androidX64 : Uint32(), Abi.fuchsiaArm64 :
        Uint32(), Abi.fuchsiaX64 : Uint32(), Abi.iosArm : Uint32(),
        Abi.iosArm64 : Uint32(), Abi.iosX64 : Uint32(), Abi.linuxArm :
        Uint32(), Abi.linuxArm64 : Uint32(), Abi.linuxIA32 : Uint32(),
        Abi.linuxX64 : Uint32(), Abi.linuxRiscv32 : Uint32(),
        Abi.linuxRiscv64 : Uint32(), Abi.macosArm64 : Uint32(),
        Abi.macosX64 : Uint32(), Abi.windowsArm64 : Uint32(),
        Abi.windowsIA32 : Uint32(), Abi.windowsX64 : Uint32()})

Constructors
------------

[UnsignedInt](unsignedint/unsignedint)()

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
<https://api.dart.dev/stable/2.18.5/dart-ffi/UnsignedInt-class.html>
:::
