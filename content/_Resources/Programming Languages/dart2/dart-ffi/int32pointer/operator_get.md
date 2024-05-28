[dart:ffi](../../dart-ffi/dart-ffi-library){._links-link}

operator \[\] method
====================

::: {.section .multi-line-signature}
[int](../../dart-core/int-class) operator \[\](

1.  [int](../../dart-core/int-class) index

)
:::

The 32-bit two\'s complement integer at `address + 4 * index`.

A Dart integer is truncated to 32 bits (as if by `.toSigned(32)`) before
being stored, and the 32-bit value is sign-extended when it is loaded.

The [address](../pointer/address) must be 4-byte aligned.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external int operator [](int index);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/Int32Pointer/operator_get.html>
:::
