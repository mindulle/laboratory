[dart:html](../../dart-html/dart-html-library){._links-link}

CustomEvent constructor
=======================

::: {.section .multi-line-signature}
CustomEvent(

1.  [String](../../dart-core/string-class) type,
2.  {[bool](../../dart-core/bool-class) canBubble = true,
3.  [bool](../../dart-core/bool-class) cancelable = true,
4.  [Object](../../dart-core/object-class)? detail}

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory CustomEvent(String type,
    {bool canBubble: true, bool cancelable: true, Object? detail}) {
  final CustomEvent e = document._createEvent('CustomEvent') as CustomEvent;

  e._dartDetail = detail;

  // Only try setting the detail if it's one of these types to avoid
  // first-chance exceptions. Can expand this list in the future as needed.
  if (detail is List || detail is Map || detail is String || detail is num) {
    try {
      detail = convertDartToNative_SerializedScriptValue(detail);
      e._initCustomEvent(type, canBubble, cancelable, detail);
    } catch (_) {
      e._initCustomEvent(type, canBubble, cancelable, null);
    }
  } else {
    e._initCustomEvent(type, canBubble, cancelable, null);
  }

  return e;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CustomEvent/CustomEvent.html>
:::
