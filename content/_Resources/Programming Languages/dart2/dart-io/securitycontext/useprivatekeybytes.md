[dart:io](../../dart-io/dart-io-library){._links-link}

usePrivateKeyBytes method
=========================

::: {.section .multi-line-signature}
void usePrivateKeyBytes(

1.  [List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>
    keyBytes,
2.  {[String](../../dart-core/string-class)? password}

)
:::

Sets the private key for a server certificate or client certificate.

Like [usePrivateKey](useprivatekey), but takes the contents of the file
as a list of bytes.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void usePrivateKeyBytes(List<int> keyBytes, {String? password});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/SecurityContext/usePrivateKeyBytes.html>
:::
