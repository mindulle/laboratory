[dart:isolate](../../dart-isolate/dart-isolate-library){._links-link}

RawReceivePort constructor
==========================

::: {.section .multi-line-signature}
RawReceivePort(

1.  \[[Function](../../dart-core/function-class)? handler,
2.  [String](../../dart-core/string-class) debugName = \'\'\]

)
:::

Opens a long-lived port for receiving messages.

A [RawReceivePort](../rawreceiveport-class) is low level and does not
work with [Zone](../../dart-async/zone-class)s. It cannot be paused. The
data-handler must be set before the first message is received, otherwise
the message is lost.

If `handler` is provided, it\'s set as the
[RawReceivePort.handler](handler).

The optional `debugName` parameter can be set to associate a name with
this port that can be displayed in tooling.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external factory RawReceivePort([Function? handler, String debugName = '']);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-isolate/RawReceivePort/RawReceivePort.html>
:::
