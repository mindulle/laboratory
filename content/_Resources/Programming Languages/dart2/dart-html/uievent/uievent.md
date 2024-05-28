[dart:html](../../dart-html/dart-html-library){._links-link}

UIEvent constructor
===================

::: {.section .multi-line-signature}
UIEvent(

1.  [String](../../dart-core/string-class) type,
2.  {[Window](../window-class)? view,
3.  [int](../../dart-core/int-class) detail = 0,
4.  [bool](../../dart-core/bool-class) canBubble = true,
5.  [bool](../../dart-core/bool-class) cancelable = true}

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory UIEvent(String type,
    {Window? view,
    int detail: 0,
    bool canBubble: true,
    bool cancelable: true}) {
  if (view == null) {
    view = window;
  }
  UIEvent e = document._createEvent("UIEvent") as UIEvent;
  e._initUIEvent(type, canBubble, cancelable, view, detail);
  return e;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/UIEvent/UIEvent.html>
:::
