[dart:ffi](../../dart-ffi/dart-ffi-library){._links-link}

lookupFunction\<T extends Function, F extends Function\> method
===============================================================

::: {.section .multi-line-signature}
F lookupFunction\<T extends Function, F extends Function\>(

1.  [String](../../dart-core/string-class) symbolName,
2.  {[bool](../../dart-core/bool-class) isLeaf = false}

)
:::

Looks up a native function and returns it as a Dart function.

`T` is the C function signature, and `F` is the Dart function signature.
For example:

``` {.language-c data-language="dart"}
int32_t add(int32_t a, int32_t b) {
  return a + b;
}
```

``` {.language-dart data-language="dart"}
DynamicLibrary dylib = DynamicLibrary.executable();
final add = dylib.lookupFunction<Int32 Function(Int32, Int32), int Function(int, int)>(
        'add');
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external F lookupFunction<T extends Function, F extends Function>(
    String symbolName,
    {bool isLeaf: false});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/DynamicLibraryExtension/lookupFunction.html>
:::
