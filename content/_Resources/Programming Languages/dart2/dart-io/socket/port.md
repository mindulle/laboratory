[dart:io](../../dart-io/dart-io-library){._links-link}

port property
=============

::: {#getter .section .multi-line-signature}
[int](../../dart-core/int-class) port
:::

The port used by this socket.

Throws a [SocketException](../socketexception-class) if the socket is
closed. The port is 0 if the socket is a Unix domain socket.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int get port;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Socket/port.html>
:::
