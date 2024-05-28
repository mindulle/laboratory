[dart:io](../../dart-io/dart-io-library){._links-link}

isUpgradeRequest method
=======================

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) isUpgradeRequest(

1.  [HttpRequest](../httprequest-class) request

)
:::

Checks whether the request is a valid WebSocket upgrade request.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static bool isUpgradeRequest(HttpRequest request) {
  return _WebSocketTransformerImpl._isUpgradeRequest(request);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/WebSocketTransformer/isUpgradeRequest.html>
:::
