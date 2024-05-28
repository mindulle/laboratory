[dart:io](../../dart-io/dart-io-library){._links-link}

WebSocketTransformer constructor
================================

::: {.section .multi-line-signature}
WebSocketTransformer(

1.  {dynamic protocolSelector(
    1.  [List](../../dart-core/list-class)\<[String](../../dart-core/string-class)\>
        protocols

    )?,
2.  [CompressionOptions](../compressionoptions-class) compression =
    CompressionOptions.compressionDefault}

)
:::

Create a new [WebSocketTransformer](../websockettransformer-class).

If `protocolSelector` is provided, `protocolSelector` will be called to
select what protocol to use, if any were provided by the client.
`protocolSelector` is should return either a
[String](../../dart-core/string-class) or a
[Future](../../dart-async/future-class) completing with a
[String](../../dart-core/string-class). The
[String](../../dart-core/string-class) must exist in the list of
protocols.

If `compression` is provided, the [WebSocket](../websocket-class)
created will be configured to negotiate with the specified
[CompressionOptions](../compressionoptions-class). If none is specified
then the [WebSocket](../websocket-class) will be created with the
default [CompressionOptions](../compressionoptions-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory WebSocketTransformer(
    {/*String|Future<String>*/ Function(List<String> protocols)?
        protocolSelector,
    CompressionOptions compression = CompressionOptions.compressionDefault}) {
  return _WebSocketTransformerImpl(protocolSelector, compression);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/WebSocketTransformer/WebSocketTransformer.html>
:::
