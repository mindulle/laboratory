[dart:html](../../dart-html/dart-html-library){._links-link}

MouseEvent constructor
======================

::: {.section .multi-line-signature}
MouseEvent(

1.  [String](../../dart-core/string-class) type,
2.  {[Window](../window-class)? view,
3.  [int](../../dart-core/int-class) detail = 0,
4.  [int](../../dart-core/int-class) screenX = 0,
5.  [int](../../dart-core/int-class) screenY = 0,
6.  [int](../../dart-core/int-class) clientX = 0,
7.  [int](../../dart-core/int-class) clientY = 0,
8.  [int](../../dart-core/int-class) button = 0,
9.  [bool](../../dart-core/bool-class) canBubble = true,
10. [bool](../../dart-core/bool-class) cancelable = true,
11. [bool](../../dart-core/bool-class) ctrlKey = false,
12. [bool](../../dart-core/bool-class) altKey = false,
13. [bool](../../dart-core/bool-class) shiftKey = false,
14. [bool](../../dart-core/bool-class) metaKey = false,
15. [EventTarget](../eventtarget-class)? relatedTarget}

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory MouseEvent(String type,
    {Window? view,
    int detail: 0,
    int screenX: 0,
    int screenY: 0,
    int clientX: 0,
    int clientY: 0,
    int button: 0,
    bool canBubble: true,
    bool cancelable: true,
    bool ctrlKey: false,
    bool altKey: false,
    bool shiftKey: false,
    bool metaKey: false,
    EventTarget? relatedTarget}) {
  if (view == null) {
    view = window;
  }
  MouseEvent event = document._createEvent('MouseEvent') as MouseEvent;
  event._initMouseEvent(
      type,
      canBubble,
      cancelable,
      view,
      detail,
      screenX,
      screenY,
      clientX,
      clientY,
      ctrlKey,
      altKey,
      shiftKey,
      metaKey,
      button,
      relatedTarget);
  return event;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/MouseEvent/MouseEvent.html>
:::
