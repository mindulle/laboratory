[dart:io](../../dart-io/dart-io-library){._links-link}

shutdown method
===============

::: {.section .multi-line-signature}
void shutdown(

1.  [SocketDirection](../socketdirection-class) direction

)
:::

Shuts down the socket in the `direction`.

Calling [shutdown](shutdown) will never throw an exception and calling
it several times is supported. Calling shutdown with either
[SocketDirection.both](../socketdirection/both-constant) or
[SocketDirection.receive](../socketdirection/receive-constant) can
result in a
[RawSocketEvent.readClosed](../rawsocketevent/readclosed-constant)
event.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void shutdown(SocketDirection direction);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RawSocket/shutdown.html>
:::
