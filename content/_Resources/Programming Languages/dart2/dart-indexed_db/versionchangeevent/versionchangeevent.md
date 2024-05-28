[dart:indexed\_db](../../dart-indexed_db/dart-indexed_db-library){._links-link}

VersionChangeEvent constructor
==============================

::: {.section .multi-line-signature}
VersionChangeEvent(

1.  [String](../../dart-core/string-class) type,
2.  \[[Map](../../dart-core/map-class)? eventInitDict\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory VersionChangeEvent(String type, [Map? eventInitDict]) {
  if (eventInitDict != null) {
    var eventInitDict_1 = convertDartToNative_Dictionary(eventInitDict);
    return VersionChangeEvent._create_1(type, eventInitDict_1);
  }
  return VersionChangeEvent._create_2(type);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-indexed_db/VersionChangeEvent/VersionChangeEvent.html>
:::
