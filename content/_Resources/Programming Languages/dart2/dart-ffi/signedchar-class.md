[dart:ffi](../dart-ffi/dart-ffi-library){._links-link}

SignedChar class
================

The C `signed char` type.

Typically a signed 8-bit integer. For a guaranteed 8-bit integer, use
[Int8](int8-class) with the C `int8_t` type. For an `unsigned char`, use
[UnsignedChar](unsignedchar-class).

The [SignedChar](signedchar-class) type is a native type, and should not
be constructed in Dart code. It occurs only in native type signatures
and as annotation on [Struct](struct-class) and [Union](union-class)
fields.

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [NativeType](nativetype-class)
    -   [AbiSpecificInteger](abispecificinteger-class)
    -   SignedChar

Annotations

:   -   \@Since(\'2.17\')
    -   @[AbiSpecificIntegerMapping](abispecificintegermapping-class)({Abi.androidArm
        : Int8(), Abi.androidArm64 : Int8(), Abi.androidIA32 : Int8(),
        Abi.androidX64 : Int8(), Abi.fuchsiaArm64 : Int8(),
        Abi.fuchsiaX64 : Int8(), Abi.iosArm : Int8(), Abi.iosArm64 :
        Int8(), Abi.iosX64 : Int8(), Abi.linuxArm : Int8(),
        Abi.linuxArm64 : Int8(), Abi.linuxIA32 : Int8(), Abi.linuxX64 :
        Int8(), Abi.linuxRiscv32 : Int8(), Abi.linuxRiscv64 : Int8(),
        Abi.macosArm64 : Int8(), Abi.macosX64 : Int8(), Abi.windowsArm64
        : Int8(), Abi.windowsIA32 : Int8(), Abi.windowsX64 : Int8()})

Constructors
------------

[SignedChar](signedchar/signedchar)()

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
<https://api.dart.dev/stable/2.18.5/dart-ffi/SignedChar-class.html>
:::
