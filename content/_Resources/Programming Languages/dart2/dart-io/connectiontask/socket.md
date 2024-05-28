[dart:io](../../dart-io/dart-io-library){._links-link}

socket property
===============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<S\> socket

::: {.features}
final
:::
:::

A `Future` that completes with value that `S.connect()` would return
unless [cancel](cancel) is called on this
[ConnectionTask](../connectiontask-class).

If [cancel](cancel) is called, the future completes with a
[SocketException](../socketexception-class) error whose message
indicates that the connection attempt was cancelled.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
final Future<S> socket;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/ConnectionTask/socket.html>
:::
