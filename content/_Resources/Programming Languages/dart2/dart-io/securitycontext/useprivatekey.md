[dart:io](../../dart-io/dart-io-library){._links-link}

usePrivateKey method
====================

::: {.section .multi-line-signature}
void usePrivateKey(

1.  [String](../../dart-core/string-class) file,
2.  {[String](../../dart-core/string-class)? password}

)
:::

Sets the private key for a server certificate or client certificate.

A secure connection using this SecurityContext will use this key with
the server or client certificate to sign and decrypt messages. `file` is
the path to a PEM or PKCS12 file containing an encrypted private key,
encrypted with `password`. Assuming it is well-formatted, all other
contents of `file` are ignored. An unencrypted file can be used, but
this is not usual.

NB: This function calls [File.readAsBytesSync](../file/readasbytessync),
and will block on file IO. Prefer using
[usePrivateKeyBytes](useprivatekeybytes).

iOS note: Only PKCS12 data is supported. It should contain both the
private key and the certificate chain. On iOS one call to
[usePrivateKey](useprivatekey) with this data is used instead of two
calls to [useCertificateChain](usecertificatechain) and
[usePrivateKey](useprivatekey).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void usePrivateKey(String file, {String? password});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/SecurityContext/usePrivateKey.html>
:::
