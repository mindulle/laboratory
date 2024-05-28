[dart:html](../../dart-html/dart-html-library){._links-link}

onDoubleClick property
======================

::: {#getter .section .multi-line-signature}
[Stream](../../dart-async/stream-class)\<[Event](../event-class)\>
onDoubleClick

::: {.features}
\@DomName(\'GlobalEventHandlers.ondblclick\')
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@DomName('GlobalEventHandlers.ondblclick')
Stream<Event> get onDoubleClick => doubleClickEvent.forTarget(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/GlobalEventHandlers/onDoubleClick.html>
:::
