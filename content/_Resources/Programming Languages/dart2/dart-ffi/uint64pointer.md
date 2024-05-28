[dart:ffi](../dart-ffi/dart-ffi-library){._links-link}

Uint64Pointer extension
=======================

Extension on [Pointer](pointer-class) specialized for the type argument
[Uint64](uint64-class).

on

:   -   [Pointer](pointer-class)\<[Uint64](uint64-class)\>

Properties {#instance-properties}
----------

[value](uint64pointer/value) ↔ [int](../dart-core/int-class)

::: {.features}
read / write
:::

The 64-bit unsigned integer at [address](pointer/address).

Methods {#instance-methods}
-------

[asTypedList](uint64pointer/astypedlist)([int](../dart-core/int-class) length) → [Uint64List](../dart-typed_data/uint64list-class)
:   Creates a typed list view backed by memory in the address space.

Operators
---------

[operator \[\]](uint64pointer/operator_get)([int](../dart-core/int-class) index) → [int](../dart-core/int-class)
:   The 64-bit unsigned integer at `address + 8 * index`.

[operator \[\]=](uint64pointer/operator_put)([int](../dart-core/int-class) index, [int](../dart-core/int-class) value) → void
:   The 64-bit unsigned integer at `address + 8 * index`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/Uint64Pointer.html>
:::
