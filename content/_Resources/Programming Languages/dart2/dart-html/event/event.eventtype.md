[dart:html](../../dart-html/dart-html-library){._links-link}

Event.eventType constructor
===========================

::: {.section .multi-line-signature}
Event.eventType(

1.  [String](../../dart-core/string-class) type,
2.  [String](../../dart-core/string-class) name,
3.  {[bool](../../dart-core/bool-class) canBubble = true,
4.  [bool](../../dart-core/bool-class) cancelable = true}

)
:::

Creates a new Event object of the specified type.

This is analogous to document.createEvent. Normally events should be
created via their constructors, if available.

``` {.language-dart data-language="dart"}
var e = new Event.type('MouseEvent', 'mousedown', true, true);
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Event.eventType(String type, String name,
    {bool canBubble: true, bool cancelable: true}) {
  final Event e = document._createEvent(type);
  e._initEvent(name, canBubble, cancelable);
  return e;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Event/Event.eventType.html>
:::
