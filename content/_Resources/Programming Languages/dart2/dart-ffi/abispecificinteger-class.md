[dart:ffi](../dart-ffi/dart-ffi-library){._links-link}

AbiSpecificInteger class
========================

The supertype of all [Abi](abi-class)-specific integer types.

[Abi](abi-class)-specific integers should extend this class and annotate
it with [AbiSpecificIntegerMapping](abispecificintegermapping-class) to
declare the integer size and signedness for
[Abi.values](abi/values-constant).

For example:

``` {.language-dart data-language="dart"}
/// The C `uintptr_t` type.
///
/// The [UintPtr] type is a native type, and should not be constructed in
/// Dart code.
/// It occurs only in native type signatures and as annotation on [Struct]
/// and [Union] fields.
@AbiSpecificIntegerMapping({
  Abi.androidArm: Uint32(),
  Abi.androidArm64: Uint64(),
  Abi.androidIA32: Uint32(),
  Abi.androidX64: Uint64(),
  Abi.fuchsiaArm64: Uint64(),
  Abi.fuchsiaX64: Uint64(),
  Abi.iosArm: Uint32(),
  Abi.iosArm64: Uint64(),
  Abi.linuxArm: Uint32(),
  Abi.linuxArm64: Uint64(),
  Abi.linuxIA32: Uint32(),
  Abi.linuxX64: Uint64(),
  Abi.linuxRiscv32: Uint32(),
  Abi.linuxRiscv64: Uint64(),
  Abi.macosArm64: Uint64(),
  Abi.macosX64: Uint64(),
  Abi.windowsIA32: Uint32(),
  Abi.windowsX64: Uint64(),
})
class UintPtr extends AbiSpecificInteger {
  const UintPtr();
}
```

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [NativeType](nativetype-class)
    -   AbiSpecificInteger

Implementers

:   -   [Char](char-class)
    -   [Int](int-class)
    -   [IntPtr](intptr-class)
    -   [Long](long-class)
    -   [LongLong](longlong-class)
    -   [Short](short-class)
    -   [SignedChar](signedchar-class)
    -   [Size](size-class)
    -   [UintPtr](uintptr-class)
    -   [UnsignedChar](unsignedchar-class)
    -   [UnsignedInt](unsignedint-class)
    -   [UnsignedLong](unsignedlong-class)
    -   [UnsignedLongLong](unsignedlonglong-class)
    -   [UnsignedShort](unsignedshort-class)
    -   [WChar](wchar-class)

Annotations

:   -   \@Since(\'2.16\')

Constructors
------------

[AbiSpecificInteger](abispecificinteger/abispecificinteger)()

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
<https://api.dart.dev/stable/2.18.5/dart-ffi/AbiSpecificInteger-class.html>
:::
