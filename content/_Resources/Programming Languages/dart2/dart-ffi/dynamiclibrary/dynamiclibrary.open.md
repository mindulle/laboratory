[dart:ffi](../../dart-ffi/dart-ffi-library){._links-link}

DynamicLibrary.open constructor
===============================

::: {.section .multi-line-signature}
DynamicLibrary.open(

1.  [String](../../dart-core/string-class) path

)
:::

Loads a library file and provides access to its symbols.

The `path` must refer to a native library file which can be successfully
loaded.

Calling this function multiple times with the same `path`, even across
different isolates, only loads the library into the DartVM process once.
Multiple loads of the same library file produces
[DynamicLibrary](../dynamiclibrary-class) objects which are equal
(`==`), but not [identical](../../dart-core/identical).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external factory DynamicLibrary.open(String path);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/DynamicLibrary/DynamicLibrary.open.html>
:::
