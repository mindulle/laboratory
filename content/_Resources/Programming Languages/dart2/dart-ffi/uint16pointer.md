[dart:ffi](../dart-ffi/dart-ffi-library){._links-link}

Uint16Pointer extension
=======================

Extension on [Pointer](pointer-class) specialized for the type argument
[Uint16](uint16-class).

on

:   -   [Pointer](pointer-class)\<[Uint16](uint16-class)\>

Properties {#instance-properties}
----------

[value](uint16pointer/value) ↔ [int](../dart-core/int-class)

::: {.features}
read / write
:::

The 16-bit unsigned integer at [address](pointer/address).

Methods {#instance-methods}
-------

[asTypedList](uint16pointer/astypedlist)([int](../dart-core/int-class) length) → [Uint16List](../dart-typed_data/uint16list-class)
:   Creates a typed list view backed by memory in the address space.

Operators
---------

[operator \[\]](uint16pointer/operator_get)([int](../dart-core/int-class) index) → [int](../dart-core/int-class)
:   The 16-bit unsigned integer at `address + 2 * index`.

[operator \[\]=](uint16pointer/operator_put)([int](../dart-core/int-class) index, [int](../dart-core/int-class) value) → void
:   The 16-bit unsigned integer at `address + 2 * index`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/Uint16Pointer.html>
:::
