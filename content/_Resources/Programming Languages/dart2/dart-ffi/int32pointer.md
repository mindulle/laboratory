[dart:ffi](../dart-ffi/dart-ffi-library){._links-link}

Int32Pointer extension
======================

Extension on [Pointer](pointer-class) specialized for the type argument
[Int32](int32-class).

on

:   -   [Pointer](pointer-class)\<[Int32](int32-class)\>

Properties {#instance-properties}
----------

[value](int32pointer/value) ↔ [int](../dart-core/int-class)

::: {.features}
read / write
:::

The 32-bit two\'s complement integer at [address](pointer/address).

Methods {#instance-methods}
-------

[asTypedList](int32pointer/astypedlist)([int](../dart-core/int-class) length) → [Int32List](../dart-typed_data/int32list-class)
:   Creates a typed list view backed by memory in the address space.

Operators
---------

[operator \[\]](int32pointer/operator_get)([int](../dart-core/int-class) index) → [int](../dart-core/int-class)
:   The 32-bit two\'s complement integer at `address + 4 * index`.

[operator \[\]=](int32pointer/operator_put)([int](../dart-core/int-class) index, [int](../dart-core/int-class) value) → void
:   The 32-bit two\'s complement integer at `address + 4 * index`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/Int32Pointer.html>
:::
