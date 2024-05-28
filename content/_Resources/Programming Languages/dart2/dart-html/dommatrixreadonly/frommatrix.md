[dart:html](../../dart-html/dart-html-library){._links-link}

fromMatrix method
=================

::: {.section .multi-line-signature}
[DomMatrixReadOnly](../dommatrixreadonly-class) fromMatrix(

1.  \[[Map](../../dart-core/map-class)? other\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static DomMatrixReadOnly fromMatrix([Map? other]) {
  if (other != null) {
    var other_1 = convertDartToNative_Dictionary(other);
    return _fromMatrix_1(other_1);
  }
  return _fromMatrix_2();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/DomMatrixReadOnly/fromMatrix.html>
:::
