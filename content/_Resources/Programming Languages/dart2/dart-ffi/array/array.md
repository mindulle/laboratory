[dart:ffi](../../dart-ffi/dart-ffi-library){._links-link}

Array\<T extends NativeType\> constructor
=========================================

::: {.section .multi-line-signature}
const Array\<T extends NativeType\>(

1.  [int](../../dart-core/int-class) dimension1,
2.  \[[int](../../dart-core/int-class) dimension2,
3.  [int](../../dart-core/int-class) dimension3,
4.  [int](../../dart-core/int-class) dimension4,
5.  [int](../../dart-core/int-class) dimension5\]

)
:::

Const constructor to specify [Array](../array-class) dimensions in
[Struct](../struct-class)s.

``` {.language-dart data-language="dart"}
class MyStruct extends Struct {
  @Array(8)
  external Array<Uint8> inlineArray;

  @Array(2, 2, 2)
  external Array<Array<Array<Uint8>>> threeDimensionalInlineArray;
}
```

Do not invoke in normal code.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
const factory Array(int dimension1,
    [int dimension2,
    int dimension3,
    int dimension4,
    int dimension5]) = _ArraySize<T>;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/Array/Array.html>
:::
