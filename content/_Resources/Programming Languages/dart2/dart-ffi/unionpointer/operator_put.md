[dart:ffi](../../dart-ffi/dart-ffi-library){._links-link}

operator \[\]= method
=====================

::: {.section .multi-line-signature}
void operator \[\]=(

1.  [int](../../dart-core/int-class) index,
2.  T value

)
:::

Copies the `value` union into native memory, starting at
`address * sizeOf<T>() * index`.

This extension method must be invoked on a receiver of type `Pointer<T>`
where `T` is a compile-time constant type.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external void operator []=(int index, T value);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/UnionPointer/operator_put.html>
:::
