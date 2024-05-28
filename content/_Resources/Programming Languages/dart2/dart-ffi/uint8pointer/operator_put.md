[dart:ffi](../../dart-ffi/dart-ffi-library){._links-link}

operator \[\]= method
=====================

::: {.section .multi-line-signature}
void operator \[\]=(

1.  [int](../../dart-core/int-class) index,
2.  [int](../../dart-core/int-class) value

)
:::

The 8-bit unsigned integer at `address + index`.

A Dart integer is truncated to 8 bits (as if by `.toUnsigned(8)`) before
being stored, and the 8-bit value is zero-extended when it is loaded.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external void operator []=(int index, int value);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/Uint8Pointer/operator_put.html>
:::
