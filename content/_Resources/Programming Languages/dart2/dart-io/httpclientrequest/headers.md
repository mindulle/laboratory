[dart:io](../../dart-io/dart-io-library){._links-link}

headers property
================

::: {#getter .section .multi-line-signature}
[HttpHeaders](../httpheaders-class) headers
:::

Returns the client request headers.

The client request headers can be modified until the client request body
is written to or closed. After that they become immutable.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
HttpHeaders get headers;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpClientRequest/headers.html>
:::
