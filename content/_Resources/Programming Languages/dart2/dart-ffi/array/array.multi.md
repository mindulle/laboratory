[dart:ffi](../../dart-ffi/dart-ffi-library){._links-link}

Array\<T extends NativeType\>.multi constructor
===============================================

::: {.section .multi-line-signature}
const Array\<T extends NativeType\>.multi(

1.  [List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>
    dimensions

)
:::

Const constructor to specify [Array](../array-class) dimensions in
[Struct](../struct-class)s.

``` {.language-dart data-language="dart"}
class MyStruct extends Struct {
  @Array.multi([2, 2, 2])
  external Array<Array<Array<Uint8>>> threeDimensionalInlineArray;

  @Array.multi([2, 2, 2, 2, 2, 2, 2, 2])
  external Array<Array<Array<Array<Array<Array<Array<Array<Uint8>>>>>>>> eightDimensionalInlineArray;
}
```

Do not invoke in normal code.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
const factory Array.multi(List<int> dimensions) = _ArraySize<T>.multi;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/Array/Array.multi.html>
:::
