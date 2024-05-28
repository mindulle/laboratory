[dart:isolate](../../dart-isolate/dart-isolate-library){._links-link}

TransferableTypedData.fromList constructor
==========================================

::: {.section .multi-line-signature}
TransferableTypedData.fromList(

1.  [List](../../dart-core/list-class)\<[TypedData](../../dart-typed_data/typeddata-class)\>
    list

)
:::

Creates a new [TransferableTypedData](../transferabletypeddata-class)
containing the bytes of `list`.

It must be possible to create a single
[Uint8List](../../dart-typed_data/uint8list-class) containing the bytes,
so if there are more bytes than what the platform allows in a single
[Uint8List](../../dart-typed_data/uint8list-class), then creation fails.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external factory TransferableTypedData.fromList(List<TypedData> list);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-isolate/TransferableTypedData/TransferableTypedData.fromList.html>
:::
