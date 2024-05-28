[dart:ffi](../dart-ffi/dart-ffi-library){._links-link}

Int8Pointer extension
=====================

Extension on [Pointer](pointer-class) specialized for the type argument
[Int8](int8-class).

on

:   -   [Pointer](pointer-class)\<[Int8](int8-class)\>

Properties {#instance-properties}
----------

[value](int8pointer/value) ↔ [int](../dart-core/int-class)

::: {.features}
read / write
:::

The 8-bit two\'s complement integer at [address](pointer/address).

Methods {#instance-methods}
-------

[asTypedList](int8pointer/astypedlist)([int](../dart-core/int-class) length) → [Int8List](../dart-typed_data/int8list-class)
:   Creates a typed list view backed by memory in the address space.

Operators
---------

[operator \[\]](int8pointer/operator_get)([int](../dart-core/int-class) index) → [int](../dart-core/int-class)
:   The 8-bit two\'s complement integer at `address + index`.

[operator \[\]=](int8pointer/operator_put)([int](../dart-core/int-class) index, [int](../dart-core/int-class) value) → void
:   The 8-bit two\'s complement integer at `address + index`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/Int8Pointer.html>
:::
