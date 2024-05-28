[dart:io](../../dart-io/dart-io-library){._links-link}

setClientAuthoritiesBytes method
================================

::: {.section .multi-line-signature}
void setClientAuthoritiesBytes(

1.  [List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>
    authCertBytes,
2.  {[String](../../dart-core/string-class)? password}

)
:::

Sets the list of authority names that a
[SecureServerSocket](../secureserversocket-class) will advertise as
accepted, when requesting a client certificate from a connecting client.

Like [setClientAuthorities](setclientauthorities) but takes the contents
of the file.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void setClientAuthoritiesBytes(List<int> authCertBytes, {String? password});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/SecurityContext/setClientAuthoritiesBytes.html>
:::
