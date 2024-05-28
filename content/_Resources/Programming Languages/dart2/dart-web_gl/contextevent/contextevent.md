[dart:web\_gl](../../dart-web_gl/dart-web_gl-library){._links-link}

ContextEvent constructor
========================

::: {.section .multi-line-signature}
ContextEvent(

1.  [String](../../dart-core/string-class) type,
2.  \[[Map](../../dart-core/map-class)? eventInit\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory ContextEvent(String type, [Map? eventInit]) {
  if (eventInit != null) {
    var eventInit_1 = convertDartToNative_Dictionary(eventInit);
    return ContextEvent._create_1(type, eventInit_1);
  }
  return ContextEvent._create_2(type);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-web_gl/ContextEvent/ContextEvent.html>
:::
