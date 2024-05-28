[dart:html](../../dart-html/dart-html-library){._links-link}

removeEventListener method
==========================

::: {.section .multi-line-signature}
void removeEventListener(

1.  [String](../../dart-core/string-class) type,
2.  [EventListener](../eventlistener)? listener,
3.  \[[bool](../../dart-core/bool-class)? useCapture\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void removeEventListener(String type, EventListener? listener,
    [bool? useCapture]) {
  // TODO(leafp): This check is avoid a bug in our dispatch code when
  // listener is null.  The browser treats this call as a no-op in this
  // case, so it's fine to short-circuit it, but we should not have to.
  if (listener != null) {
    _removeEventListener(type, listener, useCapture);
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/EventTarget/removeEventListener.html>
:::
