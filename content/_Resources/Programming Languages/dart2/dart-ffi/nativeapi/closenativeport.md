[dart:ffi](../../dart-ffi/dart-ffi-library){._links-link}

closeNativePort property
========================

::: {#getter .section .multi-line-signature}
[Pointer](../pointer-class)\<[NativeFunction](../nativefunction-class)\<[Int8](../int8-class)
Function([Int64](../int64-class))\>\> closeNativePort
:::

A function pointer to
`bool Dart_CloseNativePort(Dart_Port native_port_id)` in
`dart_native_api.h`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external static Pointer<NativeFunction<Int8 Function(Int64)>>
    get closeNativePort;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/NativeApi/closeNativePort.html>
:::
