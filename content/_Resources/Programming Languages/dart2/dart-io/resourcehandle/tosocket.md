[dart:io](../../dart-io/dart-io-library){._links-link}

toSocket method
===============

::: {.section .multi-line-signature}
[Socket](../socket-class) toSocket()
:::

Extracts opened socket from resource handle.

If this resource handle is not a socket handle, the behavior of the
returned [Socket](../socket-class) is completely unspecified. Be very
careful to avoid using a handle incorrectly.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Socket toSocket();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/ResourceHandle/toSocket.html>
:::
