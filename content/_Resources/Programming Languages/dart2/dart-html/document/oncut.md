[dart:html](../../dart-html/dart-html-library){._links-link}

onCut property
==============

::: {#getter .section .multi-line-signature}
[Stream](../../dart-async/stream-class)\<[ClipboardEvent](../clipboardevent-class)\>
onCut
:::

Stream of `cut` events handled by this [Document](../document-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<ClipboardEvent> get onCut => Element.cutEvent.forTarget(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Document/onCut.html>
:::
