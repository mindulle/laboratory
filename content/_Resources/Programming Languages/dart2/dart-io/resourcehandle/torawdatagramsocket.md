[dart:io](../../dart-io/dart-io-library){._links-link}

toRawDatagramSocket method
==========================

::: {.section .multi-line-signature}
[RawDatagramSocket](../rawdatagramsocket-class) toRawDatagramSocket()
:::

Extracts opened raw datagram socket from resource handle.

If this resource handle is not a datagram socket handle, the behavior of
the returned [RawDatagramSocket](../rawdatagramsocket-class) is
completely unspecified. Be very careful to avoid using a handle
incorrectly.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
RawDatagramSocket toRawDatagramSocket();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/ResourceHandle/toRawDatagramSocket.html>
:::
