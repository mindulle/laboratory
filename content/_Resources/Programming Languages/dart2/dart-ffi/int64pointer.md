[dart:ffi](../dart-ffi/dart-ffi-library){._links-link}

Int64Pointer extension
======================

Extension on [Pointer](pointer-class) specialized for the type argument
[Int64](int64-class).

on

:   -   [Pointer](pointer-class)\<[Int64](int64-class)\>

Properties {#instance-properties}
----------

[value](int64pointer/value) ↔ [int](../dart-core/int-class)

::: {.features}
read / write
:::

The 64-bit two\'s complement integer at [address](pointer/address).

Methods {#instance-methods}
-------

[asTypedList](int64pointer/astypedlist)([int](../dart-core/int-class) length) → [Int64List](../dart-typed_data/int64list-class)
:   Creates a typed list view backed by memory in the address space.

Operators
---------

[operator \[\]](int64pointer/operator_get)([int](../dart-core/int-class) index) → [int](../dart-core/int-class)
:   The 64-bit two\'s complement integer at `address + 8 * index`.

[operator \[\]=](int64pointer/operator_put)([int](../dart-core/int-class) index, [int](../dart-core/int-class) value) → void
:   The 64-bit two\'s complement integer at `address + 8 * index`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/Int64Pointer.html>
:::
