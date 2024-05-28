[dart:isolate](../../dart-isolate/dart-isolate-library){._links-link}

ReceivePort constructor
=======================

::: {.section .multi-line-signature}
ReceivePort(

1.  \[[String](../../dart-core/string-class) debugName = \'\'\]

)
:::

Opens a long-lived port for receiving messages.

A [ReceivePort](../receiveport-class) is a non-broadcast stream. This
means that it buffers incoming messages until a listener is registered.
Only one listener can receive messages. See
[Stream.asBroadcastStream](../../dart-async/stream/asbroadcaststream)
for transforming the port to a broadcast stream.

The optional `debugName` parameter can be set to associate a name with
this port that can be displayed in tooling.

A receive port is closed by canceling its subscription.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external factory ReceivePort([String debugName = '']);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-isolate/ReceivePort/ReceivePort.html>
:::
