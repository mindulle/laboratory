[dart:io](../../dart-io/dart-io-library){._links-link}

setClientAuthorities method
===========================

::: {.section .multi-line-signature}
void setClientAuthorities(

1.  [String](../../dart-core/string-class) file,
2.  {[String](../../dart-core/string-class)? password}

)
:::

Sets the list of authority names that a
[SecureServerSocket](../secureserversocket-class) will advertise as
accepted when requesting a client certificate from a connecting client.

The `file` is a PEM or PKCS12 file containing the accepted signing
authority certificates - the authority names are extracted from the
certificates. For PKCS12 files, `password` is the password for the file.
For PEM files, `password` is ignored. Assuming it is well-formatted, all
other contents of `file` are ignored.

NB: This function calls [File.readAsBytesSync](../file/readasbytessync),
and will block on file IO. Prefer using
[setClientAuthoritiesBytes](setclientauthoritiesbytes).

iOS note: This call is not supported.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void setClientAuthorities(String file, {String? password});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/SecurityContext/setClientAuthorities.html>
:::
