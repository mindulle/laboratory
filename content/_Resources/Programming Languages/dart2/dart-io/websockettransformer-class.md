[dart:io](../dart-io/dart-io-library){._links-link}

WebSocketTransformer class
==========================

The [WebSocketTransformer](websockettransformer-class) provides the
ability to upgrade a [HttpRequest](httprequest-class) to a
[WebSocket](websocket-class) connection. It supports both upgrading a
single [HttpRequest](httprequest-class) and upgrading a stream of
[HttpRequest](httprequest-class)s.

To upgrade a single [HttpRequest](httprequest-class) use the static
[upgrade](websockettransformer/upgrade) method.

``` {.language-dart data-language="dart"}
HttpServer server;
server.listen((request) {
  if (...) {
    WebSocketTransformer.upgrade(request).then((websocket) {
      ...
    });
  } else {
    // Do normal HTTP request processing.
  }
});
```

To transform a stream of [HttpRequest](httprequest-class) events as it
implements a stream transformer that transforms a stream of HttpRequest
into a stream of WebSockets by upgrading each HttpRequest from the HTTP
or HTTPS server, to the WebSocket protocol.

``` {.language-dart data-language="dart"}
server.transform(new WebSocketTransformer()).listen((webSocket) => ...);
```

This transformer strives to implement WebSockets as specified by
RFC6455.

Implemented types

:   -   [StreamTransformer](../dart-async/streamtransformer-class)\<[HttpRequest](httprequest-class),
        [WebSocket](websocket-class)\>

Constructors
------------

[WebSocketTransformer](websockettransformer/websockettransformer)({dynamic
protocolSelector([List](../dart-core/list-class)\<[String](../dart-core/string-class)\>
protocols)?, [CompressionOptions](compressionoptions-class) compression
= CompressionOptions.compressionDefault})

::: {.constructor-modifier .features}
factory
:::

Create a new [WebSocketTransformer](websockettransformer-class).

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[bind](../dart-async/streamtransformer/bind)([Stream](../dart-async/stream-class)\<[HttpRequest](httprequest-class)\>
stream) →
[Stream](../dart-async/stream-class)\<[WebSocket](websocket-class)\>

::: {.features}
inherited
:::

Transforms the provided `stream`.

[cast](../dart-async/streamtransformer/cast)\<RS, RT\>() →
[StreamTransformer](../dart-async/streamtransformer-class)\<RS, RT\>

::: {.features}
inherited
:::

Provides a `StreamTransformer<RS, RT>` view of this stream transformer.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

Operators
---------

[operator
==](../dart-core/object/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

Static Methods
--------------

[isUpgradeRequest](websockettransformer/isupgraderequest)([HttpRequest](httprequest-class) request) → [bool](../dart-core/bool-class)
:   Checks whether the request is a valid WebSocket upgrade request.

[upgrade](websockettransformer/upgrade)([HttpRequest](httprequest-class) request, {dynamic protocolSelector([List](../dart-core/list-class)\<[String](../dart-core/string-class)\> protocols)?, [CompressionOptions](compressionoptions-class) compression = CompressionOptions.compressionDefault}) → [Future](../dart-async/future-class)\<[WebSocket](websocket-class)\>
:   Upgrades a [HttpRequest](httprequest-class) to a `WebSocket`
    connection. If the request is not a valid WebSocket upgrade request
    an HTTP response with status code 500 will be returned. Otherwise
    the returned future will complete with the `WebSocket` when the
    upgrade process is complete.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/WebSocketTransformer-class.html>
:::
