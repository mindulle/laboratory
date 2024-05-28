[dart:io](../../dart-io/dart-io-library){._links-link}

setTrustedCertificatesBytes method
==================================

::: {.section .multi-line-signature}
void setTrustedCertificatesBytes(

1.  [List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>
    certBytes,
2.  {[String](../../dart-core/string-class)? password}

)
:::

Add a certificate to the set of trusted X509 certificates used by
[SecureSocket](../securesocket-class) client connections.

Like [setTrustedCertificates](settrustedcertificates) but takes the
contents of the file.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void setTrustedCertificatesBytes(List<int> certBytes, {String? password});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/SecurityContext/setTrustedCertificatesBytes.html>
:::
