[dart:html](../../dart-html/dart-html-library){._links-link}

matrixTransform method
======================

::: {.section .multi-line-signature}
[DomPoint](../dompoint-class) matrixTransform(

1.  \[[Map](../../dart-core/map-class)? matrix\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
DomPoint matrixTransform([Map? matrix]) {
  if (matrix != null) {
    var matrix_1 = convertDartToNative_Dictionary(matrix);
    return _matrixTransform_1(matrix_1);
  }
  return _matrixTransform_2();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/DomPointReadOnly/matrixTransform.html>
:::
