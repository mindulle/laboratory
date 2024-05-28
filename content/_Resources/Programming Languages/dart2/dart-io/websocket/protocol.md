[dart:io](../../dart-io/dart-io-library){._links-link}

protocol property
=================

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class)? protocol
:::

The protocol property is initially the empty string. After the WebSocket
connection is established the value is the subprotocol selected by the
server. If no subprotocol is negotiated the value will remain `null`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String? get protocol;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/WebSocket/protocol.html>
:::
