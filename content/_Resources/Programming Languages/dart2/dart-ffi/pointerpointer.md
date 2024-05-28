[dart:ffi](../dart-ffi/dart-ffi-library){._links-link}

PointerPointer\<T extends NativeType\> extension
================================================

Extension on [Pointer](pointer-class) specialized for the type argument
[Pointer](pointer-class).

on

:   -   [Pointer](pointer-class)\<[Pointer](pointer-class)\<T\>\>

Properties {#instance-properties}
----------

[value](pointerpointer/value) ↔ [Pointer](pointer-class)\<T\>

::: {.features}
read / write
:::

The pointer at [address](pointer/address).

Operators
---------

[operator \[\]](pointerpointer/operator_get)([int](../dart-core/int-class) index) → [Pointer](pointer-class)\<T\>
:   Load a Dart value from this location offset by `index`.

[operator \[\]=](pointerpointer/operator_put)([int](../dart-core/int-class) index, [Pointer](pointer-class)\<T\> value) → void
:   Store a Dart value into this location offset by `index`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/PointerPointer.html>
:::
