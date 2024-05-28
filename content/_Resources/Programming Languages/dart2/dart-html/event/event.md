[dart:html](../../dart-html/dart-html-library){._links-link}

Event constructor
=================

::: {.section .multi-line-signature}
Event(

1.  [String](../../dart-core/string-class) type,
2.  {[bool](../../dart-core/bool-class) canBubble = true,
3.  [bool](../../dart-core/bool-class) cancelable = true}

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Event(String type, {bool canBubble: true, bool cancelable: true}) {
  return new Event.eventType('Event', type,
      canBubble: canBubble, cancelable: cancelable);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Event/Event.html>
:::
