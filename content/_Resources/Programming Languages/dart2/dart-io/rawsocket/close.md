[dart:io](../../dart-io/dart-io-library){._links-link}

close method
============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[RawSocket](../rawsocket-class)\>
close()
:::

Closes the socket.

Returns a future that completes with this socket when the underlying
connection is completely destroyed.

Calling [close](close) will never throw an exception and calling it
several times is supported. Calling [close](close) can result in a
[RawSocketEvent.readClosed](../rawsocketevent/readclosed-constant)
event.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<RawSocket> close();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RawSocket/close.html>
:::
