[dart:html](../../dart-html/dart-html-library){._links-link}

KeyEvent constructor
====================

::: {.section .multi-line-signature}
KeyEvent(

1.  [String](../../dart-core/string-class) type,
2.  {[Window](../window-class)? view,
3.  [bool](../../dart-core/bool-class) canBubble = true,
4.  [bool](../../dart-core/bool-class) cancelable = true,
5.  [int](../../dart-core/int-class) keyCode = 0,
6.  [int](../../dart-core/int-class) charCode = 0,
7.  [int](../../dart-core/int-class) location = 1,
8.  [bool](../../dart-core/bool-class) ctrlKey = false,
9.  [bool](../../dart-core/bool-class) altKey = false,
10. [bool](../../dart-core/bool-class) shiftKey = false,
11. [bool](../../dart-core/bool-class) metaKey = false,
12. [EventTarget](../eventtarget-class)? currentTarget}

)
:::

Programmatically create a new KeyEvent (and KeyboardEvent).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory KeyEvent(String type,
    {Window? view,
    bool canBubble: true,
    bool cancelable: true,
    int keyCode: 0,
    int charCode: 0,
    int location: 1,
    bool ctrlKey: false,
    bool altKey: false,
    bool shiftKey: false,
    bool metaKey: false,
    EventTarget? currentTarget}) {
  if (view == null) {
    view = window;
  }

  dynamic eventObj;

  // Currently this works on everything but Safari. Safari throws an
  // "Attempting to change access mechanism for an unconfigurable property"
  // TypeError when trying to do the Object.defineProperty hack, so we avoid
  // this branch if possible.
  // Also, if we want this branch to work in FF, we also need to modify
  // _initKeyboardEvent to also take charCode and keyCode values to
  // initialize initKeyEvent.

  eventObj = new Event.eventType('KeyboardEvent', type,
      canBubble: canBubble, cancelable: cancelable);

  // Chromium Hack
  JS(
      'void',
      "Object.defineProperty(#, 'keyCode', {"
          "  get : function() { return this.keyCodeVal; } })",
      eventObj);
  JS(
      'void',
      "Object.defineProperty(#, 'which', {"
          "  get : function() { return this.keyCodeVal; } })",
      eventObj);
  JS(
      'void',
      "Object.defineProperty(#, 'charCode', {"
          "  get : function() { return this.charCodeVal; } })",
      eventObj);

  var keyIdentifier = _convertToHexString(charCode, keyCode);
  eventObj._initKeyboardEvent(type, canBubble, cancelable, view,
      keyIdentifier, location, ctrlKey, altKey, shiftKey, metaKey);
  JS('void', '#.keyCodeVal = #', eventObj, keyCode);
  JS('void', '#.charCodeVal = #', eventObj, charCode);

  // Tell dart2js that it smells like a KeyboardEvent!
  setDispatchProperty(eventObj, _keyboardEventDispatchRecord);

  var keyEvent = new KeyEvent.wrap(eventObj);
  if (keyEvent._currentTarget == null) {
    keyEvent._currentTarget = currentTarget == null ? window : currentTarget;
  }
  return keyEvent;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/KeyEvent/KeyEvent.html>
:::
