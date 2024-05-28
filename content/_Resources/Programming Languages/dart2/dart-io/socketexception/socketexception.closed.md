[dart:io](../../dart-io/dart-io-library){._links-link}

SocketException.closed constructor
==================================

::: {.section .multi-line-signature}
const SocketException.closed()
:::

Creates an exception reporting that a socket was used after it was
closed.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
const SocketException.closed()
    : message = 'Socket has been closed',
      osError = null,
      address = null,
      port = null;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/SocketException/SocketException.closed.html>
:::
