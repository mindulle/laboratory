[dart:ffi](../../dart-ffi/dart-ffi-library){._links-link}

operator \[\] method
====================

::: {.section .multi-line-signature}
T operator \[\](

1.  [int](../../dart-core/int-class) index

)
:::

Creates a reference to access the fields of this union backed by native
memory at `address + sizeOf<T>() * index`.

The [address](../pointer/address) must be aligned according to the union
alignment rules of the platform.

This extension method must be invoked on a receiver of type `Pointer<T>`
where `T` is a compile-time constant type.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external T operator [](int index);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/UnionPointer/operator_get.html>
:::
