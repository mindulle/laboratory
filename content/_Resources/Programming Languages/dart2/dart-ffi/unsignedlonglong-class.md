[dart:ffi](../dart-ffi/dart-ffi-library){._links-link}

UnsignedLongLong class
======================

The C `unsigned long long` type.

Typically an unsigned 64-bit integer. For a guaranteed 64-bit integer,
use [Uint64](uint64-class) with the C `uint64_t` type. For a signed
`long long`, use [LongLong](longlong-class).

The [UnsignedLongLong](unsignedlonglong-class) type is a native type,
and should not be constructed in Dart code. It occurs only in native
type signatures and as annotation on [Struct](struct-class) and
[Union](union-class) fields.

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [NativeType](nativetype-class)
    -   [AbiSpecificInteger](abispecificinteger-class)
    -   UnsignedLongLong

Annotations

:   -   \@Since(\'2.17\')
    -   @[AbiSpecificIntegerMapping](abispecificintegermapping-class)({Abi.androidArm
        : Uint64(), Abi.androidArm64 : Uint64(), Abi.androidIA32 :
        Uint64(), Abi.androidX64 : Uint64(), Abi.fuchsiaArm64 :
        Uint64(), Abi.fuchsiaX64 : Uint64(), Abi.iosArm : Uint64(),
        Abi.iosArm64 : Uint64(), Abi.iosX64 : Uint64(), Abi.linuxArm :
        Uint64(), Abi.linuxArm64 : Uint64(), Abi.linuxIA32 : Uint64(),
        Abi.linuxX64 : Uint64(), Abi.linuxRiscv32 : Uint64(),
        Abi.linuxRiscv64 : Uint64(), Abi.macosArm64 : Uint64(),
        Abi.macosX64 : Uint64(), Abi.windowsArm64 : Uint64(),
        Abi.windowsIA32 : Uint64(), Abi.windowsX64 : Uint64()})

Constructors
------------

[UnsignedLongLong](unsignedlonglong/unsignedlonglong)()

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
<https://api.dart.dev/stable/2.18.5/dart-ffi/UnsignedLongLong-class.html>
:::
