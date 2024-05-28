[dart:ffi](../../dart-ffi/dart-ffi-library){._links-link}

operator \[\]= method
=====================

::: {.section .multi-line-signature}
void operator \[\]=(

1.  [int](../../dart-core/int-class) index,
2.  [int](../../dart-core/int-class) value

)
:::

The 32-bit unsigned integer at `address + 4 * index`.

A Dart integer is truncated to 32 bits (as if by `.toUnsigned(32)`)
before being stored, and the 32-bit value is zero-extended when it is
loaded.

The [address](../pointer/address) must be 4-byte aligned.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external void operator []=(int index, int value);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/Uint32Pointer/operator_put.html>
:::
