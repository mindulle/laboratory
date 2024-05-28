[dart:html](../../dart-html/dart-html-library){._links-link}

DomMatrix constructor
=====================

::: {.section .multi-line-signature}
DomMatrix(

1.  \[[Object](../../dart-core/object-class)? init\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory DomMatrix([Object? init]) {
  if (init != null) {
    return DomMatrix._create_1(init);
  }
  return DomMatrix._create_2();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/DomMatrix/DomMatrix.html>
:::
