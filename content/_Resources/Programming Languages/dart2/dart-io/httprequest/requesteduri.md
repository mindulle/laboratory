[dart:io](../../dart-io/dart-io-library){._links-link}

requestedUri property
=====================

::: {#getter .section .multi-line-signature}
[Uri](../../dart-core/uri-class) requestedUri
:::

The requested URI for the request.

The returned URI is reconstructed by using http-header fields, to access
otherwise lost information, e.g. host and scheme.

To reconstruct the scheme, first \'X-Forwarded-Proto\' is checked, and
then falling back to server type.

To reconstruct the host, first \'X-Forwarded-Host\' is checked, then
\'Host\' and finally calling back to server.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Uri get requestedUri;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpRequest/requestedUri.html>
:::
