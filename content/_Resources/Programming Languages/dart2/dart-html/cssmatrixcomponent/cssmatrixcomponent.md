[dart:html](../../dart-html/dart-html-library){._links-link}

CssMatrixComponent constructor
==============================

::: {.section .multi-line-signature}
CssMatrixComponent(

1.  [DomMatrixReadOnly](../dommatrixreadonly-class) matrix,
2.  \[[Map](../../dart-core/map-class)? options\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory CssMatrixComponent(DomMatrixReadOnly matrix, [Map? options]) {
  if (options != null) {
    var options_1 = convertDartToNative_Dictionary(options);
    return CssMatrixComponent._create_1(matrix, options_1);
  }
  return CssMatrixComponent._create_2(matrix);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssMatrixComponent/CssMatrixComponent.html>
:::
