[dart:html](../../dart-html/dart-html-library){._links-link}

DocumentTimeline constructor
============================

::: {.section .multi-line-signature}
DocumentTimeline(

1.  \[[Map](../../dart-core/map-class)? options\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory DocumentTimeline([Map? options]) {
  if (options != null) {
    var options_1 = convertDartToNative_Dictionary(options);
    return DocumentTimeline._create_1(options_1);
  }
  return DocumentTimeline._create_2();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/DocumentTimeline/DocumentTimeline.html>
:::
