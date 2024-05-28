[dart:io](../../dart-io/dart-io-library){._links-link}

WebSocket.fromUpgradedSocket constructor
========================================

::: {.section .multi-line-signature}
WebSocket.fromUpgradedSocket(

1.  [Socket](../socket-class) socket,
2.  {[String](../../dart-core/string-class)? protocol,
3.  [bool](../../dart-core/bool-class)? serverSide,
4.  [CompressionOptions](../compressionoptions-class) compression =
    CompressionOptions.compressionDefault}

)
:::

Creates a WebSocket from an already-upgraded socket.

The initial WebSocket handshake must have occurred prior to this call. A
WebSocket client can automatically perform the handshake using
[WebSocket.connect](connect), while a server can do so using
[WebSocketTransformer.upgrade](../websockettransformer/upgrade). To
manually upgrade an [HttpRequest](../httprequest-class),
[HttpResponse.detachSocket](../httpresponse/detachsocket) may be called.

`protocol` should be the protocol negotiated by this handshake, if any.

`serverSide` must be passed explicitly. If it\'s `false`, the WebSocket
will act as the client and mask the messages it sends. If it\'s `true`,
it will act as the server and will not mask its messages.

If `compression` is provided, the [WebSocket](../websocket-class)
created will be configured to negotiate with the specified
[CompressionOptions](../compressionoptions-class). If none is specified
then the [WebSocket](../websocket-class) will be created with the
default [CompressionOptions](../compressionoptions-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory WebSocket.fromUpgradedSocket(Socket socket,
    {String? protocol,
    bool? serverSide,
    CompressionOptions compression = CompressionOptions.compressionDefault}) {
  if (serverSide == null) {
    throw ArgumentError("The serverSide argument must be passed "
        "explicitly to WebSocket.fromUpgradedSocket.");
  }
  return _WebSocketImpl._fromSocket(
      socket, protocol, compression, serverSide);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/WebSocket/WebSocket.fromUpgradedSocket.html>
:::
