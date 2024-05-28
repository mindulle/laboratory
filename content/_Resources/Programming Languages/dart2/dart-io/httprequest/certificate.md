[dart:io](../../dart-io/dart-io-library){._links-link}

certificate property
====================

::: {#getter .section .multi-line-signature}
[X509Certificate](../x509certificate-class)? certificate
:::

The client certificate of the client making the request.

This value is null if the connection is not a secure TLS or SSL
connection, or if the server does not request a client certificate, or
if the client does not provide one.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
X509Certificate? get certificate;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpRequest/certificate.html>
:::
