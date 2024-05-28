[dart:ffi](../dart-ffi/dart-ffi-library){._links-link}

StructPointer\<T extends Struct\> extension
===========================================

Extension on [Pointer](pointer-class) specialized for the type argument
[Struct](struct-class).

on

:   -   [Pointer](pointer-class)\<T\>

Annotations

-   \@Since(\'2.12\')

Properties {#instance-properties}
----------

[ref](structpointer/ref) ↔ T

::: {.features}
read / write
:::

A Dart view of the struct referenced by this pointer.

Operators
---------

[operator \[\]](structpointer/operator_get)([int](../dart-core/int-class) index) → T
:   Creates a reference to access the fields of this struct backed by
    native memory at `address + sizeOf<T>() * index`.

[operator \[\]=](structpointer/operator_put)([int](../dart-core/int-class) index, T value) → void
:   Copies the `value` struct into native memory, starting at
    `address * sizeOf<T>() * index`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/StructPointer.html>
:::
