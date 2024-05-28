[dart:io](../../dart-io/dart-io-library){._links-link}

HttpServer.listenOn constructor
===============================

::: {.section .multi-line-signature}
HttpServer.listenOn(

1.  [ServerSocket](../serversocket-class) serverSocket

)
:::

Attaches the HTTP server to an existing
[ServerSocket](../serversocket-class). When the
[HttpServer](../httpserver-class) is closed, the
[HttpServer](../httpserver-class) will just detach itself, closing
current connections but not closing `serverSocket`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory HttpServer.listenOn(ServerSocket serverSocket) =>
    _HttpServer.listenOn(serverSocket);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpServer/HttpServer.listenOn.html>
:::
