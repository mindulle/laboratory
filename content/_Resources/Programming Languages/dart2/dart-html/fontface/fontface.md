[dart:html](../../dart-html/dart-html-library){._links-link}

FontFace constructor
====================

::: {.section .multi-line-signature}
FontFace(

1.  [String](../../dart-core/string-class) family,
2.  [Object](../../dart-core/object-class) source,
3.  \[[Map](../../dart-core/map-class)? descriptors\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory FontFace(String family, Object source, [Map? descriptors]) {
  if (descriptors != null) {
    var descriptors_1 = convertDartToNative_Dictionary(descriptors);
    return FontFace._create_1(family, source, descriptors_1);
  }
  return FontFace._create_2(family, source);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/FontFace/FontFace.html>
:::
