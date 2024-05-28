[dart:html](../../dart-html/dart-html-library){._links-link}

WheelEvent constructor
======================

::: {.section .multi-line-signature}
WheelEvent(

1.  [String](../../dart-core/string-class) type,
2.  {[Window](../window-class)? view,
3.  [num](../../dart-core/num-class) deltaX = 0,
4.  [num](../../dart-core/num-class) deltaY = 0,
5.  [num](../../dart-core/num-class) deltaZ = 0,
6.  [int](../../dart-core/int-class) deltaMode = 0,
7.  [int](../../dart-core/int-class) detail = 0,
8.  [int](../../dart-core/int-class) screenX = 0,
9.  [int](../../dart-core/int-class) screenY = 0,
10. [int](../../dart-core/int-class) clientX = 0,
11. [int](../../dart-core/int-class) clientY = 0,
12. [int](../../dart-core/int-class) button = 0,
13. [bool](../../dart-core/bool-class) canBubble = true,
14. [bool](../../dart-core/bool-class) cancelable = true,
15. [bool](../../dart-core/bool-class) ctrlKey = false,
16. [bool](../../dart-core/bool-class) altKey = false,
17. [bool](../../dart-core/bool-class) shiftKey = false,
18. [bool](../../dart-core/bool-class) metaKey = false,
19. [EventTarget](../eventtarget-class)? relatedTarget}

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory WheelEvent(String type,
    {Window? view,
    num deltaX: 0,
    num deltaY: 0,
    num deltaZ: 0,
    int deltaMode: 0,
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
  var options = {
    'view': view,
    'deltaMode': deltaMode,
    'deltaX': deltaX,
    'deltaY': deltaY,
    'deltaZ': deltaZ,
    'detail': detail,
    'screenX': screenX,
    'screenY': screenY,
    'clientX': clientX,
    'clientY': clientY,
    'button': button,
    'bubbles': canBubble,
    'cancelable': cancelable,
    'ctrlKey': ctrlKey,
    'altKey': altKey,
    'shiftKey': shiftKey,
    'metaKey': metaKey,
    'relatedTarget': relatedTarget,
  };

  if (view == null) {
    view = window;
  }

  return JS('WheelEvent', 'new WheelEvent(#, #)', type,
      convertDartToNative_Dictionary(options));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/WheelEvent/WheelEvent.html>
:::
