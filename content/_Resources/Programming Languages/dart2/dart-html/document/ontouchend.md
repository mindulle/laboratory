[dart:html](../../dart-html/dart-html-library){._links-link}

onTouchEnd property
===================

::: {#getter .section .multi-line-signature}
[Stream](../../dart-async/stream-class)\<[TouchEvent](../touchevent-class)\>
onTouchEnd
:::

Stream of `touchend` events handled by this
[Document](../document-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<TouchEvent> get onTouchEnd => Element.touchEndEvent.forTarget(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Document/onTouchEnd.html>
:::
