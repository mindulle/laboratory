[dart:io](../../dart-io/dart-io-library){._links-link}

detachSocket method
===================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[Socket](../socket-class)\>
detachSocket(

1.  {[bool](../../dart-core/bool-class) writeHeaders = true}

)
:::

Detaches the underlying socket from the HTTP server. When the socket is
detached the HTTP server will no longer perform any operations on it.

This is normally used when a HTTP upgrade request is received and the
communication should continue with a different protocol.

If `writeHeaders` is `true`, the status line and [headers](headers) will
be written to the socket before it\'s detached. If `false`, the socket
is detached immediately, without any data written to the socket. Default
is `true`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<Socket> detachSocket({bool writeHeaders = true});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpResponse/detachSocket.html>
:::
