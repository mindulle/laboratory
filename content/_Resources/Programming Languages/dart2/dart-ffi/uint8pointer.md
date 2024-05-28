[dart:ffi](../dart-ffi/dart-ffi-library){._links-link}

Uint8Pointer extension
======================

Extension on [Pointer](pointer-class) specialized for the type argument
[Uint8](uint8-class).

on

:   -   [Pointer](pointer-class)\<[Uint8](uint8-class)\>

Properties {#instance-properties}
----------

[value](uint8pointer/value) ↔ [int](../dart-core/int-class)

::: {.features}
read / write
:::

The 8-bit unsigned integer at [address](pointer/address).

Methods {#instance-methods}
-------

[asTypedList](uint8pointer/astypedlist)([int](../dart-core/int-class) length) → [Uint8List](../dart-typed_data/uint8list-class)
:   Creates a typed list view backed by memory in the address space.

Operators
---------

[operator \[\]](uint8pointer/operator_get)([int](../dart-core/int-class) index) → [int](../dart-core/int-class)
:   The 8-bit unsigned integer at `address + index`.

[operator \[\]=](uint8pointer/operator_put)([int](../dart-core/int-class) index, [int](../dart-core/int-class) value) → void
:   The 8-bit unsigned integer at `address + index`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/Uint8Pointer.html>
:::
