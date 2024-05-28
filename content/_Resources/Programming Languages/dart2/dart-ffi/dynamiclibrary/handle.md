[dart:ffi](../../dart-ffi/dart-ffi-library){._links-link}

handle property
===============

::: {#getter .section .multi-line-signature}
[Pointer](../pointer-class)\<[Void](../void-class)\> handle
:::

The opaque handle to the dynamic library.

Similar to the return value of
[dlopen(3)](https://man7.org/linux/man-pages/man3/dlopen.3.html). Can be
used as arguments to other functions in the `dlopen` API through FFI
calls.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external Pointer<Void> get handle;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/DynamicLibrary/handle.html>
:::
