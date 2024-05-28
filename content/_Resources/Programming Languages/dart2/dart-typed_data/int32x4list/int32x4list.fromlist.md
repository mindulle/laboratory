[dart:typed\_data](../../dart-typed_data/dart-typed_data-library){._links-link}

Int32x4List.fromList constructor
================================

::: {.section .multi-line-signature}
Int32x4List.fromList(

1.  [List](../../dart-core/list-class)\<[Int32x4](../int32x4-class)\>
    elements

)
:::

Creates a [Int32x4List](../int32x4list-class) with the same length as
the `elements` list and copies over the elements.

The list is backed by a [ByteBuffer](../bytebuffer-class) containing
precisely `elements.length` times 16 bytes.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external factory Int32x4List.fromList(List<Int32x4> elements);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/Int32x4List/Int32x4List.fromList.html>
:::
