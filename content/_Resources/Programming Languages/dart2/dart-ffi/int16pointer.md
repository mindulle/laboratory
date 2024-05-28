[dart:ffi](../dart-ffi/dart-ffi-library){._links-link}

Int16Pointer extension
======================

Extension on [Pointer](pointer-class) specialized for the type argument
[Int16](int16-class).

on

:   -   [Pointer](pointer-class)\<[Int16](int16-class)\>

Properties {#instance-properties}
----------

[value](int16pointer/value) ↔ [int](../dart-core/int-class)

::: {.features}
read / write
:::

The 16-bit two\'s complement integer at [address](pointer/address).

Methods {#instance-methods}
-------

[asTypedList](int16pointer/astypedlist)([int](../dart-core/int-class) length) → [Int16List](../dart-typed_data/int16list-class)
:   Creates a typed list view backed by memory in the address space.

Operators
---------

[operator \[\]](int16pointer/operator_get)([int](../dart-core/int-class) index) → [int](../dart-core/int-class)
:   The 16-bit two\'s complement integer at `address + 2 * index`.

[operator \[\]=](int16pointer/operator_put)([int](../dart-core/int-class) index, [int](../dart-core/int-class) value) → void
:   The 16-bit two\'s complement integer at `address + 2 * index`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/Int16Pointer.html>
:::
