[dart:html](../../dart-html/dart-html-library){._links-link}

onMessage property
==================

::: {#getter .section .multi-line-signature}
[Stream](../../dart-async/stream-class)\<[MessageEvent](../messageevent-class)\>
onMessage
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<MessageEvent> get onMessage => messageEvent.forTarget(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/BroadcastChannel/onMessage.html>
:::
