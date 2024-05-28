[dart:html](../../dart-html/dart-html-library){._links-link}

KeyboardEvent constructor
=========================

::: {.section .multi-line-signature}
KeyboardEvent(

1.  [String](../../dart-core/string-class) type,
2.  {[Window](../window-class)? view,
3.  [bool](../../dart-core/bool-class) canBubble = true,
4.  [bool](../../dart-core/bool-class) cancelable = true,
5.  [int](../../dart-core/int-class)? location,
6.  [int](../../dart-core/int-class)? keyLocation,
7.  [bool](../../dart-core/bool-class) ctrlKey = false,
8.  [bool](../../dart-core/bool-class) altKey = false,
9.  [bool](../../dart-core/bool-class) shiftKey = false,
10. [bool](../../dart-core/bool-class) metaKey = false}

)
:::

Programmatically create a KeyboardEvent.

Due to browser differences, keyCode, charCode, or keyIdentifier values
cannot be specified in this base level constructor. This constructor
enables the user to programmatically create and dispatch a
[KeyboardEvent](../keyboardevent-class), but it will not contain any
particular key content. For programmatically creating keyboard events
with specific key value contents, see the custom Event
[KeyEvent](../keyevent-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory KeyboardEvent(String type,
    {Window? view,
    bool canBubble: true,
    bool cancelable: true,
    int? location,
    int? keyLocation, // Legacy alias for location
    bool ctrlKey: false,
    bool altKey: false,
    bool shiftKey: false,
    bool metaKey: false}) {
  if (view == null) {
    view = window;
  }
  location ??= keyLocation ?? 1;
  KeyboardEvent e = document._createEvent("KeyboardEvent") as KeyboardEvent;
  e._initKeyboardEvent(type, canBubble, cancelable, view, "", location,
      ctrlKey, altKey, shiftKey, metaKey);
  return e;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/KeyboardEvent/KeyboardEvent.html>
:::
