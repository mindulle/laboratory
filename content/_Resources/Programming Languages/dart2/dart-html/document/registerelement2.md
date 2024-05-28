[dart:html](../../dart-html/dart-html-library){._links-link}

registerElement2 method
=======================

::: {.section .multi-line-signature}
[Function](../../dart-core/function-class) registerElement2(

1.  [String](../../dart-core/string-class) type,
2.  \[[Map](../../dart-core/map-class)? options\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Function registerElement2(String type, [Map? options]) {
  if (options != null) {
    var options_1 = convertDartToNative_Dictionary(options);
    return _registerElement2_1(type, options_1);
  }
  return _registerElement2_2(type);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Document/registerElement2.html>
:::
