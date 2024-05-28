[dart:io](../../dart-io/dart-io-library){._links-link}

connect method
==============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[WebSocket](../websocket-class)\>
connect(

1.  [String](../../dart-core/string-class) url,
2.  {[Iterable](../../dart-core/iterable-class)\<[String](../../dart-core/string-class)\>?
    protocols,
3.  [Map](../../dart-core/map-class)\<[String](../../dart-core/string-class),
    dynamic\>? headers,
4.  [CompressionOptions](../compressionoptions-class) compression =
    CompressionOptions.compressionDefault,
5.  [HttpClient](../httpclient-class)? customClient}

)
:::

Create a new WebSocket connection. The URL supplied in `url` must use
the scheme `ws` or `wss`.

The `protocols` argument is specifying the subprotocols the client is
willing to speak.

The `headers` argument is specifying additional HTTP headers for setting
up the connection. This would typically be the `Origin` header and
potentially cookies. The keys of the map are the header fields and the
values are either String or List.

If `headers` is provided, there are a number of headers which are
controlled by the WebSocket connection process. These headers are:

-   `connection`
-   `sec-websocket-key`
-   `sec-websocket-protocol`
-   `sec-websocket-version`
-   `upgrade`

If any of these are passed in the `headers` map they will be ignored.

If the `url` contains user information this will be passed as basic
authentication when setting up the connection.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static Future<WebSocket> connect(String url,
        {Iterable<String>? protocols,
        Map<String, dynamic>? headers,
        CompressionOptions compression =
            CompressionOptions.compressionDefault,
        HttpClient? customClient}) =>
    _WebSocketImpl.connect(url, protocols, headers,
        compression: compression, customClient: customClient);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/WebSocket/connect.html>
:::
