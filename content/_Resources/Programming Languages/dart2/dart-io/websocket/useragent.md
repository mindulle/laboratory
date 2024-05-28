[dart:io](../../dart-io/dart-io-library){._links-link}

userAgent property
==================

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class)? userAgent
:::

Gets the user agent used for WebSocket connections.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static String? get userAgent => _WebSocketImpl.userAgent;
```

::: {#setter .section .multi-line-signature}
void userAgent=([String](../../dart-core/string-class)? userAgent)
:::

Sets the user agent to use for WebSocket connections.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static set userAgent(String? userAgent) {
  _WebSocketImpl.userAgent = userAgent;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/WebSocket/userAgent.html>
:::
