[dart:typed\_data](../../dart-typed_data/dart-typed_data-library){._links-link}

Float32List.fromList constructor
================================

::: {.section .multi-line-signature}
Float32List.fromList(

1.  [List](../../dart-core/list-class)\<[double](../../dart-core/double-class)\>
    elements

)
:::

Creates a [Float32List](../float32list-class) with the same length as
the `elements` list and copies over the elements.

Values are truncated to fit in the list when they are copied, the same
way storing values truncates them.

The list is backed by a [ByteBuffer](../bytebuffer-class) containing
precisely `elements.length` times 4 bytes.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external factory Float32List.fromList(List<double> elements);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/Float32List/Float32List.fromList.html>
:::
