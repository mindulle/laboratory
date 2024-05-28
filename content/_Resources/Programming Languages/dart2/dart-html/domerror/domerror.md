[dart:html](../../dart-html/dart-html-library){._links-link}

DomError constructor
====================

::: {.section .multi-line-signature}
DomError(

1.  [String](../../dart-core/string-class) name,
2.  \[[String](../../dart-core/string-class)? message\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory DomError(String name, [String? message]) {
  if (message != null) {
    return DomError._create_1(name, message);
  }
  return DomError._create_2(name);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/DomError/DomError.html>
:::
