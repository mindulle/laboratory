[dart:isolate](../../dart-isolate/dart-isolate-library){._links-link}

materialize method
==================

::: {.section .multi-line-signature}
[ByteBuffer](../../dart-typed_data/bytebuffer-class) materialize()
:::

Creates a new [ByteBuffer](../../dart-typed_data/bytebuffer-class)
containing the bytes stored in this
[TransferableTypedData](../transferabletypeddata-class).

The [TransferableTypedData](../transferabletypeddata-class) is a
cross-isolate single-use resource. This method must not be called more
than once on the same underlying transferable bytes, even if the calls
occur in different isolates.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
ByteBuffer materialize();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-isolate/TransferableTypedData/materialize.html>
:::
