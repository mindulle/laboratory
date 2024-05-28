[dart:html](../../dart-html/dart-html-library){._links-link}

onFullscreenError property
==========================

::: {#getter .section .multi-line-signature}
[Stream](../../dart-async/stream-class)\<[Event](../event-class)\>
onFullscreenError
:::

Stream of `fullscreenerror` events handled by this
[Document](../document-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<Event> get onFullscreenError =>
    Element.fullscreenErrorEvent.forTarget(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Document/onFullscreenError.html>
:::
