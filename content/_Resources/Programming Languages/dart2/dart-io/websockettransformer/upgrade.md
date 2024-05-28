[dart:io](../../dart-io/dart-io-library){._links-link}

upgrade method
==============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[WebSocket](../websocket-class)\>
upgrade(

1.  [HttpRequest](../httprequest-class) request,
2.  {dynamic protocolSelector(
    1.  [List](../../dart-core/list-class)\<[String](../../dart-core/string-class)\>
        protocols

    )?,
3.  [CompressionOptions](../compressionoptions-class) compression =
    CompressionOptions.compressionDefault}

)
:::

Upgrades a [HttpRequest](../httprequest-class) to a `WebSocket`
connection. If the request is not a valid WebSocket upgrade request an
HTTP response with status code 500 will be returned. Otherwise the
returned future will complete with the `WebSocket` when the upgrade
process is complete.

If `protocolSelector` is provided, `protocolSelector` will be called to
select what protocol to use, if any were provided by the client.
`protocolSelector` is should return either a
[String](../../dart-core/string-class) or a
[Future](../../dart-async/future-class) completing with a
[String](../../dart-core/string-class). The
[String](../../dart-core/string-class) must exist in the list of
protocols.

If `compression` is provided, the `WebSocket` created will be configured
to negotiate with the specified
[CompressionOptions](../compressionoptions-class). If none is specified
then the `WebSocket` will be created with the default
[CompressionOptions](../compressionoptions-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static Future<WebSocket> upgrade(HttpRequest request,
    {Function(List<String> protocols)? protocolSelector,
    CompressionOptions compression = CompressionOptions.compressionDefault}) {
  return _WebSocketTransformerImpl._upgrade(
      request, protocolSelector, compression);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/WebSocketTransformer/upgrade.html>
:::
