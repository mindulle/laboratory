[dart:ffi](../dart-ffi/dart-ffi-library){._links-link}

NativeFinalizerFunction typedef
===============================

::: {.section .multi-line-signature}
NativeFinalizerFunction =
[NativeFunction](nativefunction-class)\<[Void](void-class)
Function([Pointer](pointer-class)\<[Void](void-class)\> token)\>
:::

The native function type for [NativeFinalizer](nativefinalizer-class)s.

A [NativeFinalizer](nativefinalizer-class)\'s `callback` should have the
C `void nativeFinalizer(void* token)` type.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
typedef NativeFinalizerFunction
    = NativeFunction<Void Function(Pointer<Void> token)>;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/NativeFinalizerFunction.html>
:::
