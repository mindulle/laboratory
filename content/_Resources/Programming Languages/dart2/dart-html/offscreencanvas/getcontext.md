[dart:html](../../dart-html/dart-html-library){._links-link}

getContext method
=================

::: {.section .multi-line-signature}
[Object](../../dart-core/object-class)? getContext(

1.  [String](../../dart-core/string-class) contextType,
2.  \[[Map](../../dart-core/map-class)? attributes\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Object? getContext(String contextType, [Map? attributes]) {
  if (attributes != null) {
    var attributes_1 = convertDartToNative_Dictionary(attributes);
    return _getContext_1(contextType, attributes_1);
  }
  return _getContext_2(contextType);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/OffscreenCanvas/getContext.html>
:::
