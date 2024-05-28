[dart:ffi](../dart-ffi/dart-ffi-library){._links-link}

Uint32Pointer extension
=======================

Extension on [Pointer](pointer-class) specialized for the type argument
[Uint32](uint32-class).

on

:   -   [Pointer](pointer-class)\<[Uint32](uint32-class)\>

Properties {#instance-properties}
----------

[value](uint32pointer/value) ↔ [int](../dart-core/int-class)

::: {.features}
read / write
:::

The 32-bit unsigned integer at [address](pointer/address).

Methods {#instance-methods}
-------

[asTypedList](uint32pointer/astypedlist)([int](../dart-core/int-class) length) → [Uint32List](../dart-typed_data/uint32list-class)
:   Creates a typed list view backed by memory in the address space.

Operators
---------

[operator \[\]](uint32pointer/operator_get)([int](../dart-core/int-class) index) → [int](../dart-core/int-class)
:   The 32-bit unsigned integer at `address + 4 * index`.

[operator \[\]=](uint32pointer/operator_put)([int](../dart-core/int-class) index, [int](../dart-core/int-class) value) → void
:   The 32-bit unsigned integer at `address + 4 * index`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/Uint32Pointer.html>
:::
