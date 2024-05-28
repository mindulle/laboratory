[dart:ffi](../../dart-ffi/dart-ffi-library){._links-link}

operator \[\]= method
=====================

::: {.section .multi-line-signature}
void operator \[\]=(

1.  [int](../../dart-core/int-class) index,
2.  [int](../../dart-core/int-class) value

)
:::

The 64-bit two\'s complement integer at `address + 8 * index`.

The [address](../pointer/address) must be 8-byte aligned.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external void operator []=(int index, int value);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/Int64Pointer/operator_put.html>
:::
