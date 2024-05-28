[dart:ffi](../../dart-ffi/dart-ffi-library){._links-link}

nativePort property
===================

::: {#getter .section .multi-line-signature}
[int](../../dart-core/int-class) nativePort
:::

The native port of this [SendPort](../../dart-isolate/sendport-class).

The returned native port can for example be used by C code to post
messages to the connected
[ReceivePort](../../dart-isolate/receiveport-class) via
`Dart_PostCObject()` - see `dart_native_api.h`.

Only the send ports from the platform classes
[ReceivePort](../../dart-isolate/receiveport-class) and
[RawReceivePort](../../dart-isolate/rawreceiveport-class) are supported.
User-defined implementations of
[SendPort](../../dart-isolate/sendport-class) are not supported.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external int get nativePort;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/NativePort/nativePort.html>
:::
