[dart:html](../../dart-html/dart-html-library){._links-link}

sendBlob method
===============

::: {.section .multi-line-signature}
<div>

1.  \@JSName(\'send\')

</div>

void sendBlob(

1.  [Blob](../blob-class) data

)

::: {.features}
\@JSName(\'send\')
:::
:::

Transmit data to the server over this connection.

This method accepts data of type [Blob](../blob-class),
[ByteBuffer](../../dart-typed_data/bytebuffer-class),
[String](../../dart-core/string-class), or
[TypedData](../../dart-typed_data/typeddata-class). Named variants
[sendBlob](sendblob), [sendByteBuffer](sendbytebuffer),
[sendString](sendstring), or [sendTypedData](sendtypeddata), in
contrast, only accept data of the specified type.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@JSName('send')
/**
 * Transmit data to the server over this connection.
 *
 * This method accepts data of type [Blob], [ByteBuffer], [String], or
 * [TypedData]. Named variants [sendBlob], [sendByteBuffer], [sendString],
 * or [sendTypedData], in contrast, only accept data of the specified type.
 */
void sendBlob(Blob data) native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/WebSocket/sendBlob.html>
:::
