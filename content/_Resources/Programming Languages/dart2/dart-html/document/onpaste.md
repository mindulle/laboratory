[dart:html](../../dart-html/dart-html-library){._links-link}

onPaste property
================

::: {#getter .section .multi-line-signature}
[Stream](../../dart-async/stream-class)\<[ClipboardEvent](../clipboardevent-class)\>
onPaste
:::

Stream of `paste` events handled by this [Document](../document-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<ClipboardEvent> get onPaste => Element.pasteEvent.forTarget(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Document/onPaste.html>
:::
