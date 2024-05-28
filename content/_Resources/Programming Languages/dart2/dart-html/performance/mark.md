[dart:html](../../dart-html/dart-html-library){._links-link}

mark method
===========

::: {.section .multi-line-signature}
[PerformanceEntry](../performanceentry-class)? mark(

1.  [String](../../dart-core/string-class) markName,
2.  \[[Map](../../dart-core/map-class)? markOptions\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
PerformanceEntry? mark(String markName, [Map? markOptions]) {
  if (markOptions != null) {
    var markOptions_1 = convertDartToNative_Dictionary(markOptions);
    return _mark_1(markName, markOptions_1);
  }
  return _mark_2(markName);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Performance/mark.html>
:::
