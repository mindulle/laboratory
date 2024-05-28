[dart:html](../../dart-html/dart-html-library){._links-link}

send method
===========

::: {.section .multi-line-signature}
void send(

1.  dynamic data

)
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
void send(data) native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/WebSocket/send.html>
:::
