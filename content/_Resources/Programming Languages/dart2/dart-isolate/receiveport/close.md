[dart:isolate](../../dart-isolate/dart-isolate-library){._links-link}

close method
============

::: {.section .multi-line-signature}
void close()
:::

Closes the receive port.

No further events will be received by the receive port, or emitted as
stream events.

If [listen](listen) has been called and the
[StreamSubscription](../../dart-async/streamsubscription-class) has not
been canceled yet, the subscription will be closed with a \"done\"
event.

If the stream has already been canceled this method has no effect.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void close();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-isolate/ReceivePort/close.html>
:::
