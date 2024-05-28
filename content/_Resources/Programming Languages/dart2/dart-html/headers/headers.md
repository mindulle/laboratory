[dart:html](../../dart-html/dart-html-library){._links-link}

Headers constructor
===================

::: {.section .multi-line-signature}
Headers(

1.  \[[Object](../../dart-core/object-class)? init\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Headers([Object? init]) {
  if (init != null) {
    return Headers._create_1(init);
  }
  return Headers._create_2();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Headers/Headers.html>
:::
