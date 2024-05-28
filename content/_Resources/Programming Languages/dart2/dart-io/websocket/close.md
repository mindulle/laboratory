[dart:io](../../dart-io/dart-io-library){._links-link}

close method
============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) close(

1.  \[[int](../../dart-core/int-class)? code,
2.  [String](../../dart-core/string-class)? reason\]

)

::: {.features}
override
:::
:::

Closes the WebSocket connection. Set the optional `code` and `reason`
arguments to send close information to the remote peer. If they are
omitted, the peer will see
[WebSocketStatus.noStatusReceived](../websocketstatus/nostatusreceived-constant)
code with no reason.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future close([int? code, String? reason]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/WebSocket/close.html>
:::
