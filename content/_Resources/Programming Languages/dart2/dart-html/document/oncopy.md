[dart:html](../../dart-html/dart-html-library){._links-link}

onCopy property
===============

::: {#getter .section .multi-line-signature}
[Stream](../../dart-async/stream-class)\<[ClipboardEvent](../clipboardevent-class)\>
onCopy
:::

Stream of `copy` events handled by this [Document](../document-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<ClipboardEvent> get onCopy => Element.copyEvent.forTarget(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Document/onCopy.html>
:::
