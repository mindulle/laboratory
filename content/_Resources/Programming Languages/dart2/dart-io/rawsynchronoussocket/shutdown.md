[dart:io](../../dart-io/dart-io-library){._links-link}

shutdown method
===============

::: {.section .multi-line-signature}
void shutdown(

1.  [SocketDirection](../socketdirection-class) direction

)
:::

Shuts down a socket in the provided direction.

Calling shutdown will never throw an exception and calling it several
times is supported. If both
[SocketDirection.receive](../socketdirection/receive-constant) and
[SocketDirection.send](../socketdirection/send-constant) directions are
closed, the socket is closed completely, the same as if
[closeSync](closesync) has been called.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void shutdown(SocketDirection direction);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RawSynchronousSocket/shutdown.html>
:::
