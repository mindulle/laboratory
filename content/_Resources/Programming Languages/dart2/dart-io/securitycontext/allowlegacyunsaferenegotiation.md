[dart:io](../../dart-io/dart-io-library){._links-link}

allowLegacyUnsafeRenegotiation property
=======================================

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) allowLegacyUnsafeRenegotiation

::: {.features}
read / write
:::
:::

If `true`, the [SecurityContext](../securitycontext-class) will allow
TLS renegotiation. Renegotiation is only supported as a client and the
HelloRequest must be received at a quiet point in the application
protocol. This is sufficient to support the legacy use case of
requesting a new client certificate between an HTTP request and response
in (unpipelined) HTTP/1.1. NOTE: Renegotiation is an extremely
problematic protocol feature and should only be used to communicate with
legacy servers in environments where it is known to be safe.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
abstract bool allowLegacyUnsafeRenegotiation;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/SecurityContext/allowLegacyUnsafeRenegotiation.html>
:::
