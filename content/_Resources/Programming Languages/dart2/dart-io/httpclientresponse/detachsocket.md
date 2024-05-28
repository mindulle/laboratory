[dart:io](../../dart-io/dart-io-library){._links-link}

detachSocket method
===================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[Socket](../socket-class)\>
detachSocket()
:::

Detach the underlying socket from the HTTP client. When the socket is
detached the HTTP client will no longer perform any operations on it.

This is normally used when a HTTP upgrade is negotiated and the
communication should continue with a different protocol.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<Socket> detachSocket();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpClientResponse/detachSocket.html>
:::
