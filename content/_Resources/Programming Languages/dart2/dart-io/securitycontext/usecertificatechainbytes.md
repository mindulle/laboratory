[dart:io](../../dart-io/dart-io-library){._links-link}

useCertificateChainBytes method
===============================

::: {.section .multi-line-signature}
void useCertificateChainBytes(

1.  [List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>
    chainBytes,
2.  {[String](../../dart-core/string-class)? password}

)
:::

Sets the chain of X509 certificates served by
[SecureServerSocket](../secureserversocket-class) when making secure
connections, including the server certificate.

Like [useCertificateChain](usecertificatechain) but takes the contents
of the file.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void useCertificateChainBytes(List<int> chainBytes, {String? password});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/SecurityContext/useCertificateChainBytes.html>
:::
