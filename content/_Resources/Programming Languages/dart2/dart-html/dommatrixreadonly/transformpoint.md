[dart:html](../../dart-html/dart-html-library){._links-link}

transformPoint method
=====================

::: {.section .multi-line-signature}
[DomPoint](../dompoint-class) transformPoint(

1.  \[[Map](../../dart-core/map-class)? point\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
DomPoint transformPoint([Map? point]) {
  if (point != null) {
    var point_1 = convertDartToNative_Dictionary(point);
    return _transformPoint_1(point_1);
  }
  return _transformPoint_2();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/DomMatrixReadOnly/transformPoint.html>
:::
