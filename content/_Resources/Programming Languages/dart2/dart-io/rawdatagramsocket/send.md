[dart:io](../../dart-io/dart-io-library){._links-link}

send method
===========

::: {.section .multi-line-signature}
[int](../../dart-core/int-class) send(

1.  [List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>
    buffer,
2.  [InternetAddress](../internetaddress-class) address,
3.  [int](../../dart-core/int-class) port

)
:::

Sends a datagram.

Returns the number of bytes written. This will always be either the size
of `buffer` or `0`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int send(List<int> buffer, InternetAddress address, int port);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RawDatagramSocket/send.html>
:::
