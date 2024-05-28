[dart:html](../../dart-html/dart-html-library){._links-link}

onDoubleClick property
======================

::: {#getter .section .multi-line-signature}
[Stream](../../dart-async/stream-class)\<[Event](../event-class)\>
onDoubleClick

::: {.features}
\@DomName(\'Window.ondblclick\'), override
:::
:::

Stream of `doubleclick` events handled by this
[Window](../window-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@DomName('Window.ondblclick')
Stream<Event> get onDoubleClick => Element.doubleClickEvent.forTarget(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Window/onDoubleClick.html>
:::
