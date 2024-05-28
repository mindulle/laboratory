[dart:ffi](../../dart-ffi/dart-ffi-library){._links-link}

newNativePort property
======================

::: {#getter .section .multi-line-signature}
[Pointer](../pointer-class)\<[NativeFunction](../nativefunction-class)\<[Int64](../int64-class)
Function([Pointer](../pointer-class)\<[Uint8](../uint8-class)\>,
[Pointer](../pointer-class)\<[NativeFunction](../nativefunction-class)\<[Dart\_NativeMessageHandler](../dart_nativemessagehandler)\>\>,
[Int8](../int8-class))\>\> newNativePort
:::

A function pointer to

``` {.language-c data-language="dart"}
Dart_Port Dart_NewNativePort(const char* name,
                             Dart_NativeMessageHandler handler,
                             bool handle_concurrently)
```

in `dart_native_api.h`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external static Pointer<
    NativeFunction<
        Int64 Function(
            Pointer<Uint8>,
            Pointer<NativeFunction<Dart_NativeMessageHandler>>,
            Int8)>> get newNativePort;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/NativeApi/newNativePort.html>
:::
