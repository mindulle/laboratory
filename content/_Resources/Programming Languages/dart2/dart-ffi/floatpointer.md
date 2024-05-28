[dart:ffi](../dart-ffi/dart-ffi-library){._links-link}

FloatPointer extension
======================

Extension on [Pointer](pointer-class) specialized for the type argument
[Float](float-class).

on

:   -   [Pointer](pointer-class)\<[Float](float-class)\>

Properties {#instance-properties}
----------

[value](floatpointer/value) ↔ [double](../dart-core/double-class)

::: {.features}
read / write
:::

The float at [address](pointer/address).

Methods {#instance-methods}
-------

[asTypedList](floatpointer/astypedlist)([int](../dart-core/int-class) length) → [Float32List](../dart-typed_data/float32list-class)
:   Creates a typed list view backed by memory in the address space.

Operators
---------

[operator \[\]](floatpointer/operator_get)([int](../dart-core/int-class) index) → [double](../dart-core/double-class)
:   The float at `address + 4 * index`.

[operator \[\]=](floatpointer/operator_put)([int](../dart-core/int-class) index, [double](../dart-core/double-class) value) → void
:   The float at `address + 4 * index`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/FloatPointer.html>
:::
