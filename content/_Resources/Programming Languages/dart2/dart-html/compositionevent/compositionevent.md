[dart:html](../../dart-html/dart-html-library){._links-link}

CompositionEvent constructor
============================

::: {.section .multi-line-signature}
CompositionEvent(

1.  [String](../../dart-core/string-class) type,
2.  {[bool](../../dart-core/bool-class) canBubble = false,
3.  [bool](../../dart-core/bool-class) cancelable = false,
4.  [Window](../window-class)? view,
5.  [String](../../dart-core/string-class)? data,
6.  [String](../../dart-core/string-class)? locale}

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory CompositionEvent(String type,
    {bool canBubble: false,
    bool cancelable: false,
    Window? view,
    String? data,
    String? locale}) {
  if (view == null) {
    view = window;
  }
  CompositionEvent e =
      document._createEvent("CompositionEvent") as CompositionEvent;

  if (Device.isFirefox) {
    // Firefox requires the locale parameter that isn't supported elsewhere.
    JS('void', '#.initCompositionEvent(#, #, #, #, #, #)', e, type, canBubble,
        cancelable, view, data, locale);
  } else {
    e._initCompositionEvent(type, canBubble, cancelable, view, data);
  }

  return e;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CompositionEvent/CompositionEvent.html>
:::
