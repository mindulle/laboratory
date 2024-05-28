[dart:io](../../dart-io/dart-io-library){._links-link}

peerCertificate property
========================

::: {#getter .section .multi-line-signature}
[X509Certificate](../x509certificate-class)? peerCertificate
:::

The peer certificate for a connected SecureSocket.

If this [SecureSocket](../securesocket-class) is the server end of a
secure socket connection, [peerCertificate](peercertificate) will return
the client certificate, or `null` if no client certificate was received.
If this socket is the client end, [peerCertificate](peercertificate)
will return the server\'s certificate.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
X509Certificate? get peerCertificate;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/SecureSocket/peerCertificate.html>
:::
