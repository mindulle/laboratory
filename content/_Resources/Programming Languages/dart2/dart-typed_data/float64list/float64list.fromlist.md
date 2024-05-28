[dart:typed\_data](../../dart-typed_data/dart-typed_data-library){._links-link}

Float64List.fromList constructor
================================

::: {.section .multi-line-signature}
Float64List.fromList(

1.  [List](../../dart-core/list-class)\<[double](../../dart-core/double-class)\>
    elements

)
:::

Creates a [Float64List](../float64list-class) with the same length as
the `elements` list and copies over the elements.

The list is backed by a [ByteBuffer](../bytebuffer-class) containing
precisely `elements.length` times 8 bytes.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external factory Float64List.fromList(List<double> elements);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/Float64List/Float64List.fromList.html>
:::
