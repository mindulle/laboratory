[dart:typed\_data](../../dart-typed_data/dart-typed_data-library){._links-link}

Float32x4List.fromList constructor
==================================

::: {.section .multi-line-signature}
Float32x4List.fromList(

1.  [List](../../dart-core/list-class)\<[Float32x4](../float32x4-class)\>
    elements

)
:::

Creates a [Float32x4List](../float32x4list-class) with the same length
as the `elements` list and copies over the elements.

The list is backed by a [ByteBuffer](../bytebuffer-class) containing
precisely `elements.length` times 16 bytes.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external factory Float32x4List.fromList(List<Float32x4> elements);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/Float32x4List/Float32x4List.fromList.html>
:::
