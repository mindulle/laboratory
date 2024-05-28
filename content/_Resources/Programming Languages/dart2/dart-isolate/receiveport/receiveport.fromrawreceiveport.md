[dart:isolate](../../dart-isolate/dart-isolate-library){._links-link}

ReceivePort.fromRawReceivePort constructor
==========================================

::: {.section .multi-line-signature}
ReceivePort.fromRawReceivePort(

1.  [RawReceivePort](../rawreceiveport-class) rawPort

)
:::

Creates a [ReceivePort](../receiveport-class) from a
[RawReceivePort](../rawreceiveport-class).

The handler of the given `rawPort` is overwritten during the
construction of the result.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external factory ReceivePort.fromRawReceivePort(RawReceivePort rawPort);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-isolate/ReceivePort/ReceivePort.fromRawReceivePort.html>
:::
