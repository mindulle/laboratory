[dart:ffi](../dart-ffi/dart-ffi-library){._links-link}

UnionPointer\<T extends Union\> extension
=========================================

Extension on [Pointer](pointer-class) specialized for the type argument
[Union](union-class).

on

:   -   [Pointer](pointer-class)\<T\>

Annotations

-   \@Since(\'2.14\')

Properties {#instance-properties}
----------

[ref](unionpointer/ref) ↔ T

::: {.features}
read / write
:::

A Dart view of the union referenced by this pointer.

Operators
---------

[operator \[\]](unionpointer/operator_get)([int](../dart-core/int-class) index) → T
:   Creates a reference to access the fields of this union backed by
    native memory at `address + sizeOf<T>() * index`.

[operator \[\]=](unionpointer/operator_put)([int](../dart-core/int-class) index, T value) → void
:   Copies the `value` union into native memory, starting at
    `address * sizeOf<T>() * index`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/UnionPointer.html>
:::
