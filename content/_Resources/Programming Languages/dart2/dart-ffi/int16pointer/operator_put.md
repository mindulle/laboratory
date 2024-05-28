[dart:ffi](../../dart-ffi/dart-ffi-library){._links-link}

operator \[\]= method
=====================

::: {.section .multi-line-signature}
void operator \[\]=(

1.  [int](../../dart-core/int-class) index,
2.  [int](../../dart-core/int-class) value

)
:::

The 16-bit two\'s complement integer at `address + 2 * index`.

A Dart integer is truncated to 16 bits (as if by `.toSigned(16)`) before
being stored, and the 16-bit value is sign-extended when it is loaded.

The [address](../pointer/address) must be 2-byte aligned.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external void operator []=(int index, int value);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/Int16Pointer/operator_put.html>
:::
