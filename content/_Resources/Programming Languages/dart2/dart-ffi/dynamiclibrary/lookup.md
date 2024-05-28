[dart:ffi](../../dart-ffi/dart-ffi-library){._links-link}

lookup\<T extends NativeType\> method
=====================================

::: {.section .multi-line-signature}
[Pointer](../pointer-class)\<T\> lookup\<T extends NativeType\>(

1.  [String](../../dart-core/string-class) symbolName

)
:::

Looks up a symbol in the [DynamicLibrary](../dynamiclibrary-class) and
returns its address in memory.

Similar to the functionality of the
[dlsym(3)](https://man7.org/linux/man-pages/man3/dlsym.3.html) system
call.

The symbol must be provided by the dynamic library. To check whether the
library provides such symbol, use [providesSymbol](providessymbol).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external Pointer<T> lookup<T extends NativeType>(String symbolName);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/DynamicLibrary/lookup.html>
:::
