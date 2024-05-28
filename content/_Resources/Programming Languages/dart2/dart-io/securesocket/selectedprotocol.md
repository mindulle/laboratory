[dart:io](../../dart-io/dart-io-library){._links-link}

selectedProtocol property
=========================

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class)? selectedProtocol
:::

The protocol which was selected during ALPN protocol negotiation.

Returns `null` if one of the peers does not have support for ALPN, did
not specify a list of supported ALPN protocols or there was no common
protocol between client and server.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String? get selectedProtocol;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/SecureSocket/selectedProtocol.html>
:::
