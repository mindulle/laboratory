[dart:io](../../dart-io/dart-io-library){._links-link}

persistentConnection property
=============================

::: {#getter .section .multi-line-signature}
[bool](../../dart-core/bool-class) persistentConnection
:::

Gets the persistent connection state returned by the server.

If the persistent connection state needs to be set, it must be set
before the body is written to. Setting the persistent connection state
after writing to the body will throw a `StateError`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool get persistentConnection;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpClientResponse/persistentConnection.html>
:::
