[dart:io](../../dart-io/dart-io-library){._links-link}

useCertificateChain method
==========================

::: {.section .multi-line-signature}
void useCertificateChain(

1.  [String](../../dart-core/string-class) file,
2.  {[String](../../dart-core/string-class)? password}

)
:::

Sets the chain of X509 certificates served by
[SecureServerSocket](../secureserversocket-class) when making secure
connections, including the server certificate.

`file` is a PEM or PKCS12 file containing X509 certificates, starting
with the root authority and intermediate authorities forming the signed
chain to the server certificate, and ending with the server certificate.
The private key for the server certificate is set by
[usePrivateKey](useprivatekey). For PKCS12 files, `password` is the
password for the file. For PEM files, `password` is ignored. Assuming it
is well-formatted, all other contents of `file` are ignored.

NB: This function calls [File.readAsBytesSync](../file/readasbytessync),
and will block on file IO. Prefer using
[useCertificateChainBytes](usecertificatechainbytes).

iOS note: As noted above, [usePrivateKey](useprivatekey) does the job of
both that call and this one. On iOS, this call is a no-op.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void useCertificateChain(String file, {String? password});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/SecurityContext/useCertificateChain.html>
:::
