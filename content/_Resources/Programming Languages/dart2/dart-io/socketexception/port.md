[dart:io](../../dart-io/dart-io-library){._links-link}

port property
=============

::: {.section .multi-line-signature}
[int](../../dart-core/int-class)? port

::: {.features}
final
:::
:::

The port of the socket giving rise to the exception.

This is either the source or destination address of a socket, or it can
be `null` if no socket end-point was involved in the cause of the
exception.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
final int? port;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/SocketException/port.html>
:::
