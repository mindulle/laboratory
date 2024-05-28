[dart:io](../../dart-io/dart-io-library){._links-link}

renegotiate method
==================

::: {.section .multi-line-signature}
<div>

1.  @[Deprecated](../../dart-core/deprecated-class)(\"Not implemented\")

</div>

void renegotiate(

1.  {[bool](../../dart-core/bool-class) useSessionCache = true,
2.  [bool](../../dart-core/bool-class) requestClientCertificate = false,
3.  [bool](../../dart-core/bool-class) requireClientCertificate = false}

)

::: {.features}
@[Deprecated](../../dart-core/deprecated-class)(\"Not implemented\")
:::
:::

Does nothing.

The original intent was to allow TLS renegotiation of existing secure
connections.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Deprecated("Not implemented")
void renegotiate(
    {bool useSessionCache = true,
    bool requestClientCertificate = false,
    bool requireClientCertificate = false});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RawSecureSocket/renegotiate.html>
:::
