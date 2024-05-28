[dart:html](../../dart-html/dart-html-library){._links-link}

onClose property
================

::: {#getter .section .multi-line-signature}
[Stream](../../dart-async/stream-class)\<[CloseEvent](../closeevent-class)\>
onClose
:::

Stream of `close` events handled by this
[WebSocket](../websocket-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<CloseEvent> get onClose => closeEvent.forTarget(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/WebSocket/onClose.html>
:::
