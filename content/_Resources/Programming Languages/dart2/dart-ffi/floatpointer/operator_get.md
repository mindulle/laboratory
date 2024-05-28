[dart:ffi](../../dart-ffi/dart-ffi-library){._links-link}

operator \[\] method
====================

::: {.section .multi-line-signature}
[double](../../dart-core/double-class) operator \[\](

1.  [int](../../dart-core/int-class) index

)
:::

The float at `address + 4 * index`.

A Dart double loses precision before being stored, and the float value
is converted to a double when it is loaded.

The [address](../pointer/address) must be 4-byte aligned.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external double operator [](int index);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/FloatPointer/operator_get.html>
:::
