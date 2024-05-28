[dart:io](../../dart-io/dart-io-library){._links-link}

setTrustedCertificates method
=============================

::: {.section .multi-line-signature}
void setTrustedCertificates(

1.  [String](../../dart-core/string-class) file,
2.  {[String](../../dart-core/string-class)? password}

)
:::

Add a certificate to the set of trusted X509 certificates used by
[SecureSocket](../securesocket-class) client connections.

`file` is the path to a PEM or PKCS12 file containing X509 certificates,
usually root certificates from certificate authorities. For PKCS12
files, `password` is the password for the file. For PEM files,
`password` is ignored. Assuming it is well-formatted, all other contents
of `file` are ignored.

NB: This function calls [File.readAsBytesSync](../file/readasbytessync),
and will block on file IO. Prefer using
[setTrustedCertificatesBytes](settrustedcertificatesbytes).

iOS note: On iOS, this call takes only the bytes for a single DER
encoded X509 certificate. It may be called multiple times to add
multiple trusted certificates to the context. A DER encoded certificate
can be obtained from a PEM encoded certificate by using the openssl
tool:

``` {.language-bash data-language="dart"}
$ openssl x509 -outform der -in cert.pem -out cert.der
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void setTrustedCertificates(String file, {String? password});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/SecurityContext/setTrustedCertificates.html>
:::
