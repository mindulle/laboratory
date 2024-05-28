[dart:ffi](../../dart-ffi/dart-ffi-library){._links-link}

operator \[\] method
====================

::: {.section .multi-line-signature}
[int](../../dart-core/int-class) operator \[\](

1.  [int](../../dart-core/int-class) index

)
:::

The 8-bit unsigned integer at `address + index`.

A Dart integer is truncated to 8 bits (as if by `.toUnsigned(8)`) before
being stored, and the 8-bit value is zero-extended when it is loaded.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external int operator [](int index);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/Uint8Pointer/operator_get.html>
:::
