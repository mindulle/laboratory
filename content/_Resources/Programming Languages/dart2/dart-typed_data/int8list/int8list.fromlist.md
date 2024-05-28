[dart:typed\_data](../../dart-typed_data/dart-typed_data-library){._links-link}

Int8List.fromList constructor
=============================

::: {.section .multi-line-signature}
Int8List.fromList(

1.  [List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>
    elements

)
:::

Creates a [Int8List](../int8list-class) with the same length as the
`elements` list and copies over the elements.

Values are truncated to fit in the list when they are copied, the same
way storing values truncates them.

The list is backed by a [ByteBuffer](../bytebuffer-class) containing
precisely `elements.length` bytes.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external factory Int8List.fromList(List<int> elements);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/Int8List/Int8List.fromList.html>
:::
