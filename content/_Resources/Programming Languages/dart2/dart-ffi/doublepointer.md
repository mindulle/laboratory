[dart:ffi](../dart-ffi/dart-ffi-library){._links-link}

DoublePointer extension
=======================

Extension on [Pointer](pointer-class) specialized for the type argument
[Double](double-class).

on

:   -   [Pointer](pointer-class)\<[Double](double-class)\>

Properties {#instance-properties}
----------

[value](doublepointer/value) ↔ [double](../dart-core/double-class)

::: {.features}
read / write
:::

The double at [address](pointer/address).

Methods {#instance-methods}
-------

[asTypedList](doublepointer/astypedlist)([int](../dart-core/int-class) length) → [Float64List](../dart-typed_data/float64list-class)
:   Creates a typed list view backed by memory in the address space.

Operators
---------

[operator \[\]](doublepointer/operator_get)([int](../dart-core/int-class) index) → [double](../dart-core/double-class)
:   The double at `address + 8 * index`.

[operator \[\]=](doublepointer/operator_put)([int](../dart-core/int-class) index, [double](../dart-core/double-class) value) → void
:   The double at `address + 8 * index`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/DoublePointer.html>
:::
