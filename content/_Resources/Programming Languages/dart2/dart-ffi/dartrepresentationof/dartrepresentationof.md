[dart:ffi](../../dart-ffi/dart-ffi-library){._links-link}

DartRepresentationOf constructor
================================

::: {.section .multi-line-signature}
const DartRepresentationOf(

1.  [String](../../dart-core/string-class) nativeType

)
:::

Represents the Dart type corresponding to a
[NativeType](../nativetype-class).

[Int8](../int8-class) -\> [int](../../dart-core/int-class)
[Int16](../int16-class) -\> [int](../../dart-core/int-class)
[Int32](../int32-class) -\> [int](../../dart-core/int-class)
[Int64](../int64-class) -\> [int](../../dart-core/int-class)
[Uint8](../uint8-class) -\> [int](../../dart-core/int-class)
[Uint16](../uint16-class) -\> [int](../../dart-core/int-class)
[Uint32](../uint32-class) -\> [int](../../dart-core/int-class)
[Uint64](../uint64-class) -\> [int](../../dart-core/int-class)
[IntPtr](../intptr-class) -\> [int](../../dart-core/int-class)
[Double](../double-class) -\> [double](../../dart-core/double-class)
[Float](../float-class) -\> [double](../../dart-core/double-class)
[Pointer](../pointer-class) -\> [Pointer](../pointer-class)
[NativeFunction](../nativefunction-class) S1 Function(S2, S3) where
DartRepresentationOf(Tn) -\> Sn T extends Struct -\> T

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
const DartRepresentationOf(String nativeType);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/DartRepresentationOf/DartRepresentationOf.html>
:::
