[dart:io](../../dart-io/dart-io-library){._links-link}

pingInterval property
=====================

::: {.section .multi-line-signature}
[Duration](../../dart-core/duration-class)? pingInterval

::: {.features}
read / write
:::
:::

The interval between ping signals.

A ping message is sent every [pingInterval](pinginterval), starting at
the first [pingInterval](pinginterval) after a new value has been
assigned or a pong message has been received. If a ping message is not
answered by a pong message from the peer, the `WebSocket` is assumed
disconnected and the connection is closed with a
[WebSocketStatus.goingAway](../websocketstatus/goingaway-constant) close
code. When a ping signal is sent, the pong message must be received
within [pingInterval](pinginterval).

There are never two outstanding pings at any given time, and the next
ping timer starts when the pong is received.

Set the [pingInterval](pinginterval) to `null` to disable sending ping
messages.

The default value is `null`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Duration? pingInterval;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/WebSocket/pingInterval.html>
:::
