[dart:ffi](../../dart-ffi/dart-ffi-library){._links-link}

DynamicLibrary.process constructor
==================================

::: {.section .multi-line-signature}
DynamicLibrary.process()
:::

Creates a [DynamicLibrary](../dynamiclibrary-class) holding all global
symbols.

Any symbol in a library currently loaded with global visibility
(including the executable itself) may be resolved through this library.

This feature is not available on Windows.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external factory DynamicLibrary.process();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/DynamicLibrary/DynamicLibrary.process.html>
:::
