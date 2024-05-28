[dart:html](../../dart-html/dart-html-library){._links-link}

onDoubleClick property
======================

::: {#getter .section .multi-line-signature}
[ElementStream](../elementstream-class)\<[Event](../event-class)\>
onDoubleClick

::: {.features}
\@DomName(\'Element.ondblclick\'), override
:::
:::

Stream of `doubleclick` events handled by this
[Element](../element-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@DomName('Element.ondblclick')
ElementStream<Event> get onDoubleClick => doubleClickEvent.forElement(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/onDoubleClick.html>
:::
