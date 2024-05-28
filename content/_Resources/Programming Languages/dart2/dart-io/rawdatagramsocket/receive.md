[dart:io](../../dart-io/dart-io-library){._links-link}

receive method
==============

::: {.section .multi-line-signature}
[Datagram](../datagram-class)? receive()
:::

Receives a datagram.

Returns `null` if there are no datagrams available.

The maximum length of the datagram that can be received is 65503 bytes.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Datagram? receive();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RawDatagramSocket/receive.html>
:::
