[dart:isolate](../../dart-isolate/dart-isolate-library){._links-link}

controlPort property
====================

::: {.section .multi-line-signature}
[SendPort](../sendport-class) controlPort

::: {.features}
final
:::
:::

Control port used to send control messages to the isolate.

The control port identifies the isolate.

An `Isolate` object allows sending control messages through the control
port.

Some control messages require a specific capability to be passed along
with the message (see [pauseCapability](pausecapability) and
[terminateCapability](terminatecapability)), otherwise the message is
ignored by the isolate.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
final SendPort controlPort;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-isolate/Isolate/controlPort.html>
:::
