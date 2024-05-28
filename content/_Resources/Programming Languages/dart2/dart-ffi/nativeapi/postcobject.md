[dart:ffi](../../dart-ffi/dart-ffi-library){._links-link}

postCObject property
====================

::: {#getter .section .multi-line-signature}
[Pointer](../pointer-class)\<[NativeFunction](../nativefunction-class)\<[Int8](../int8-class)
Function([Int64](../int64-class),
[Pointer](../pointer-class)\<[Dart\_CObject](../dart_cobject-class)\>)\>\>
postCObject
:::

A function pointer to
`bool Dart_PostCObject(Dart_Port port_id, Dart_CObject* message)` in
`dart_native_api.h`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external static Pointer<
        NativeFunction<Int8 Function(Int64, Pointer<Dart_CObject>)>>
    get postCObject;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/NativeApi/postCObject.html>
:::
