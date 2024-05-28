[dart:io](../../dart-io/dart-io-library){._links-link}

tcpNoDelay constant
===================

::: {.section .multi-line-signature}
[SocketOption](../socketoption-class) const tcpNoDelay
:::

Enable or disable no-delay on the socket. If tcpNoDelay is enabled, the
socket will not buffer data internally, but instead write each data
chunk as an individual TCP packet.

tcpNoDelay is disabled by default.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const SocketOption tcpNoDelay = const SocketOption._(0);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/SocketOption/tcpNoDelay-constant.html>
:::
