[dart:html](../../dart-html/dart-html-library){._links-link}

operator \[\] method
====================

::: {.section .multi-line-signature}
[Stream](../../dart-async/stream-class)\<[Event](../event-class)\>
operator \[\](

1.  [String](../../dart-core/string-class) type

)

::: {.features}
override
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<Event> operator [](String type) {
  if (webkitEvents.keys.contains(type.toLowerCase())) {
    if (Device.isWebKit) {
      return new _ElementEventStreamImpl(
          _ptr, webkitEvents[type.toLowerCase()], false);
    }
  }
  return new _ElementEventStreamImpl(_ptr, type, false);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/ElementEvents/operator_get.html>
:::
