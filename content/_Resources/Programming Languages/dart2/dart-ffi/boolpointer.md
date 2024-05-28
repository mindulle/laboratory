[dart:ffi](../dart-ffi/dart-ffi-library){._links-link}

BoolPointer extension
=====================

Extension on [Pointer](pointer-class) specialized for the type argument
[Bool](bool-class).

on

:   -   [Pointer](pointer-class)\<[Bool](bool-class)\>

Annotations

-   \@Since(\'2.15\')

Properties {#instance-properties}
----------

[value](boolpointer/value) ↔ [bool](../dart-core/bool-class)

::: {.features}
read / write
:::

The bool at [address](pointer/address).

Operators
---------

[operator \[\]](boolpointer/operator_get)([int](../dart-core/int-class) index) → [bool](../dart-core/bool-class)
:   The bool at `address + index`.

[operator \[\]=](boolpointer/operator_put)([int](../dart-core/int-class) index, [bool](../dart-core/bool-class) value) → void
:   The bool at `address + index`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/BoolPointer.html>
:::
