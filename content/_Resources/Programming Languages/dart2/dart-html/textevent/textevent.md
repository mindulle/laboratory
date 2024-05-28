[dart:html](../../dart-html/dart-html-library){._links-link}

TextEvent constructor
=====================

::: {.section .multi-line-signature}
TextEvent(

1.  [String](../../dart-core/string-class) type,
2.  {[bool](../../dart-core/bool-class) canBubble = false,
3.  [bool](../../dart-core/bool-class) cancelable = false,
4.  [Window](../window-class)? view,
5.  [String](../../dart-core/string-class)? data}

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory TextEvent(String type,
    {bool canBubble: false,
    bool cancelable: false,
    Window? view,
    String? data}) {
  if (view == null) {
    view = window;
  }
  TextEvent e = document._createEvent("TextEvent") as TextEvent;
  e._initTextEvent(type, canBubble, cancelable, view, data);
  return e;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/TextEvent/TextEvent.html>
:::
