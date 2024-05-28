[dart:html](../../dart-html/dart-html-library){._links-link}

File constructor
================

::: {.section .multi-line-signature}
File(

1.  [List](../../dart-core/list-class)\<[Object](../../dart-core/object-class)\>
    fileBits,
2.  [String](../../dart-core/string-class) fileName,
3.  \[[Map](../../dart-core/map-class)? options\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory File(List<Object> fileBits, String fileName, [Map? options]) {
  if (options != null) {
    var options_1 = convertDartToNative_Dictionary(options);
    return File._create_1(fileBits, fileName, options_1);
  }
  return File._create_2(fileBits, fileName);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/File/File.html>
:::
