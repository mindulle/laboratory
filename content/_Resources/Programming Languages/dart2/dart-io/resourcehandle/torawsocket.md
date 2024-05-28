[dart:io](../../dart-io/dart-io-library){._links-link}

toRawSocket method
==================

::: {.section .multi-line-signature}
[RawSocket](../rawsocket-class) toRawSocket()
:::

Extracts opened raw socket from resource handle.

If this resource handle is not a socket handle, the behavior of the
returned [RawSocket](../rawsocket-class) is completely unspecified. Be
very careful to avoid using a handle incorrectly.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
RawSocket toRawSocket();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/ResourceHandle/toRawSocket.html>
:::
