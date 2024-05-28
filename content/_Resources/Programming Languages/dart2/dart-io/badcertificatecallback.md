[dart:io](../dart-io/dart-io-library){._links-link}

BadCertificateCallback typedef
==============================

::: {.section .multi-line-signature}
BadCertificateCallback = [bool](../dart-core/bool-class)
Function([X509Certificate](x509certificate-class) cr,
[String](../dart-core/string-class) host, [int](../dart-core/int-class)
port)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
typedef BadCertificateCallback = bool Function(
    X509Certificate cr, String host, int port);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/BadCertificateCallback.html>
:::
