[dart:html](../../dart-html/dart-html-library){._links-link}

onPaste property
================

::: {#getter .section .multi-line-signature}
[ElementStream](../elementstream-class)\<[ClipboardEvent](../clipboardevent-class)\>
onPaste
:::

Stream of `paste` events handled by this [Element](../element-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
ElementStream<ClipboardEvent> get onPaste => pasteEvent.forElement(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/onPaste.html>
:::
