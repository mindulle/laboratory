[dart:ffi](../dart-ffi/dart-ffi-library){._links-link}

sizeOf\<T extends NativeType\> function
=======================================

::: {.section .multi-line-signature}
[int](../dart-core/int-class) sizeOf\<T extends NativeType\>()
:::

Number of bytes used by native type T.

Includes padding and alignment of structs.

This function must be invoked with a compile-time constant `T`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external int sizeOf<T extends NativeType>();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/sizeOf.html>
:::
