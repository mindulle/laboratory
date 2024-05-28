[dart:html](../../dart-html/dart-html-library){._links-link}

BackgroundFetchClickEvent constructor
=====================================

::: {.section .multi-line-signature}
BackgroundFetchClickEvent(

1.  [String](../../dart-core/string-class) type,
2.  [Map](../../dart-core/map-class) init

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory BackgroundFetchClickEvent(String type, Map init) {
  var init_1 = convertDartToNative_Dictionary(init);
  return BackgroundFetchClickEvent._create_1(type, init_1);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/BackgroundFetchClickEvent/BackgroundFetchClickEvent.html>
:::
