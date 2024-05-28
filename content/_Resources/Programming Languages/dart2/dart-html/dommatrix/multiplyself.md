[dart:html](../../dart-html/dart-html-library){._links-link}

multiplySelf method
===================

::: {.section .multi-line-signature}
[DomMatrix](../dommatrix-class) multiplySelf(

1.  \[[Map](../../dart-core/map-class)? other\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
DomMatrix multiplySelf([Map? other]) {
  if (other != null) {
    var other_1 = convertDartToNative_Dictionary(other);
    return _multiplySelf_1(other_1);
  }
  return _multiplySelf_2();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/DomMatrix/multiplySelf.html>
:::
