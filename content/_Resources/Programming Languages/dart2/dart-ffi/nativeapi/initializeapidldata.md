[dart:ffi](../../dart-ffi/dart-ffi-library){._links-link}

initializeApiDLData property
============================

::: {#getter .section .multi-line-signature}
[Pointer](../pointer-class)\<[Void](../void-class)\> initializeApiDLData

::: {.features}
\@Since(\'2.9\')
:::
:::

Pass this to `Dart_InitializeApiDL` in your native code to enable using
the symbols in `dart_api_dl.h`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Since('2.9')
external static Pointer<Void> get initializeApiDLData;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/NativeApi/initializeApiDLData.html>
:::
