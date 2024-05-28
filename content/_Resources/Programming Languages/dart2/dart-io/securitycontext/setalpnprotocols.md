[dart:io](../../dart-io/dart-io-library){._links-link}

setAlpnProtocols method
=======================

::: {.section .multi-line-signature}
void setAlpnProtocols(

1.  [List](../../dart-core/list-class)\<[String](../../dart-core/string-class)\>
    protocols,
2.  [bool](../../dart-core/bool-class) isServer

)
:::

Sets the list of application-level protocols supported by a client
connection or server connection. The ALPN (application level protocol
negotiation) extension to TLS allows a client to send a list of
protocols in the TLS client hello message, and the server to pick one
and send the selected one back in its server hello message.

Separate lists of protocols can be sent for client connections and for
server connections, using the same SecurityContext. The `isServer`
boolean argument specifies whether to set the list for server
connections or client connections.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void setAlpnProtocols(List<String> protocols, bool isServer);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/SecurityContext/setAlpnProtocols.html>
:::
