[dart:ffi](../dart-ffi/dart-ffi-library){._links-link}

AbiSpecificIntegerPointer\<T extends AbiSpecificInteger\> extension
===================================================================

Extension on [Pointer](pointer-class) specialized for the type argument
[AbiSpecificInteger](abispecificinteger-class).

on

:   -   [Pointer](pointer-class)\<T\>

Annotations

-   \@Since(\'2.16\')

Properties {#instance-properties}
----------

[value](abispecificintegerpointer/value) ↔ [int](../dart-core/int-class)

::: {.features}
read / write
:::

The integer at [address](pointer/address).

Operators
---------

[operator \[\]](abispecificintegerpointer/operator_get)([int](../dart-core/int-class) index) → [int](../dart-core/int-class)
:   The integer at `address + sizeOf<T>() * index`.

[operator \[\]=](abispecificintegerpointer/operator_put)([int](../dart-core/int-class) index, [int](../dart-core/int-class) value) → void
:   The integer at `address + sizeOf<T>() * index`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/AbiSpecificIntegerPointer.html>
:::
