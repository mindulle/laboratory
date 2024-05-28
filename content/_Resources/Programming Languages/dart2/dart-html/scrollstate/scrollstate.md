[dart:html](../../dart-html/dart-html-library){._links-link}

ScrollState constructor
=======================

::: {.section .multi-line-signature}
ScrollState(

1.  \[[Map](../../dart-core/map-class)? scrollStateInit\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory ScrollState([Map? scrollStateInit]) {
  if (scrollStateInit != null) {
    var scrollStateInit_1 = convertDartToNative_Dictionary(scrollStateInit);
    return ScrollState._create_1(scrollStateInit_1);
  }
  return ScrollState._create_2();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/ScrollState/ScrollState.html>
:::
