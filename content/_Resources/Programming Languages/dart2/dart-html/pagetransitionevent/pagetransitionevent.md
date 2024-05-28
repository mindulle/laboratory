[dart:html](../../dart-html/dart-html-library){._links-link}

PageTransitionEvent constructor
===============================

::: {.section .multi-line-signature}
PageTransitionEvent(

1.  [String](../../dart-core/string-class) type,
2.  \[[Map](../../dart-core/map-class)? eventInitDict\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory PageTransitionEvent(String type, [Map? eventInitDict]) {
  if (eventInitDict != null) {
    var eventInitDict_1 = convertDartToNative_Dictionary(eventInitDict);
    return PageTransitionEvent._create_1(type, eventInitDict_1);
  }
  return PageTransitionEvent._create_2(type);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/PageTransitionEvent/PageTransitionEvent.html>
:::
