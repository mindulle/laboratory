[dart:html](../../dart-html/dart-html-library){._links-link}

UrlSearchParams constructor
===========================

::: {.section .multi-line-signature}
UrlSearchParams(

1.  \[[Object](../../dart-core/object-class)? init\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory UrlSearchParams([Object? init]) {
  if (init != null) {
    return UrlSearchParams._create_1(init);
  }
  return UrlSearchParams._create_2();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/UrlSearchParams/UrlSearchParams.html>
:::
