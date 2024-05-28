[dart:ffi](../dart-ffi/dart-ffi-library){._links-link}

Abi class
=========

An application binary interface (ABI).

An ABI defines the memory layout of data and the function call protocol
for native code. It is usually defined by the an operating system for
each architecture that operating system runs on.

The Dart VM can run on a variety of operating systems and architectures.
Supported ABIs are represented by `Abi` objects. See
[values](abi/values-constant) for all the supported ABIs.

Annotations

:   -   \@Since(\'2.16\')

Constructors
------------

[Abi.current](abi/abi.current)()

::: {.constructor-modifier .features}
factory
:::

The ABI the Dart VM is currently running on.

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

[toString](abi/tostring)() → [String](../dart-core/string-class)

::: {.features}
override
:::

A string representation of this ABI.

Operators
---------

[operator
==](../dart-core/object/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

Constants
---------

[androidArm](abi/androidarm-constant) → const [Abi](abi-class)
:   The application binary interface for Android on the Arm
    architecture.
    <div>

    `_androidArm`

    </div>

[androidArm64](abi/androidarm64-constant) → const [Abi](abi-class)
:   The application binary interface for Android on the Arm64
    architecture.
    <div>

    `_androidArm64`

    </div>

[androidIA32](abi/androidia32-constant) → const [Abi](abi-class)
:   The application binary interface for Android on the IA32
    architecture.
    <div>

    `_androidIA32`

    </div>

[androidX64](abi/androidx64-constant) → const [Abi](abi-class)
:   The application binary interface for android on the X64
    architecture.
    <div>

    `_androidX64`

    </div>

[fuchsiaArm64](abi/fuchsiaarm64-constant) → const [Abi](abi-class)
:   The application binary interface for Fuchsia on the Arm64
    architecture.
    <div>

    `_fuchsiaArm64`

    </div>

[fuchsiaX64](abi/fuchsiax64-constant) → const [Abi](abi-class)
:   The application binary interface for Fuchsia on the X64
    architecture.
    <div>

    `_fuchsiaX64`

    </div>

[iosArm](abi/iosarm-constant) → const [Abi](abi-class)
:   The application binary interface for iOS on the Arm architecture.
    <div>

    `_iosArm`

    </div>

[iosArm64](abi/iosarm64-constant) → const [Abi](abi-class)
:   The application binary interface for iOS on the Arm64 architecture.
    <div>

    `_iosArm64`

    </div>

[iosX64](abi/iosx64-constant) → const [Abi](abi-class)
:   The application binary interface for iOS on the X64 architecture.
    <div>

    `_iosX64`

    </div>

[linuxArm](abi/linuxarm-constant) → const [Abi](abi-class)
:   The application binary interface for Linux on the Arm architecture.
    <div>

    `_linuxArm`

    </div>

[linuxArm64](abi/linuxarm64-constant) → const [Abi](abi-class)
:   The application binary interface for linux on the Arm64
    architecture.
    <div>

    `_linuxArm64`

    </div>

[linuxIA32](abi/linuxia32-constant) → const [Abi](abi-class)
:   The application binary interface for linux on the IA32 architecture.
    <div>

    `_linuxIA32`

    </div>

[linuxRiscv32](abi/linuxriscv32-constant) → const [Abi](abi-class)
:   The application binary interface for linux on 32-bit RISC-V.
    <div>

    `_linuxRiscv32`

    </div>

[linuxRiscv64](abi/linuxriscv64-constant) → const [Abi](abi-class)
:   The application binary interface for linux on 64-bit RISC-V.
    <div>

    `_linuxRiscv64`

    </div>

[linuxX64](abi/linuxx64-constant) → const [Abi](abi-class)
:   The application binary interface for linux on the X64 architecture.
    <div>

    `_linuxX64`

    </div>

[macosArm64](abi/macosarm64-constant) → const [Abi](abi-class)
:   The application binary interface for MacOS on the Arm64
    architecture.
    <div>

    `_macosArm64`

    </div>

[macosX64](abi/macosx64-constant) → const [Abi](abi-class)
:   The application binary interface for MacOS on the X64 architecture.
    <div>

    `_macosX64`

    </div>

[values](abi/values-constant) → const [List](../dart-core/list-class)\<[Abi](abi-class)\>
:   The ABIs that the DartVM can run on.
    <div>

    `[androidArm, androidArm64, androidIA32, androidX64, fuchsiaArm64, fuchsiaX64, iosArm, iosArm64, iosX64, linuxArm, linuxArm64, linuxIA32, linuxX64, linuxRiscv32, linuxRiscv64, macosArm64, macosX64, win…`

    </div>

[windowsArm64](abi/windowsarm64-constant) → const [Abi](abi-class)
:   The application binary interface for Windows on the Arm64
    architecture.
    <div>

    `_windowsArm64`

    </div>

[windowsIA32](abi/windowsia32-constant) → const [Abi](abi-class)
:   The application binary interface for Windows on the IA32
    architecture.
    <div>

    `_windowsIA32`

    </div>

[windowsX64](abi/windowsx64-constant) → const [Abi](abi-class)
:   The application binary interface for Windows on the X64
    architecture.
    <div>

    `_windowsX64`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/Abi-class.html>
:::
