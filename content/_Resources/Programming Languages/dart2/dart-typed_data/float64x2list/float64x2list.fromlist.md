[dart:typed\_data](../../dart-typed_data/dart-typed_data-library){._links-link}

Float64x2List.fromList constructor
==================================

::: {.section .multi-line-signature}
Float64x2List.fromList(

1.  [List](../../dart-core/list-class)\<[Float64x2](../float64x2-class)\>
    elements

)
:::

Creates a [Float64x2List](../float64x2list-class) with the same length
as the `elements` list and copies over the elements.

The list is backed by a [ByteBuffer](../bytebuffer-class) containing
precisely `elements.length` times 16 bytes.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external factory Float64x2List.fromList(List<Float64x2> elements);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/Float64x2List/Float64x2List.fromList.html>
:::
