[dart:html](../../dart-html/dart-html-library){._links-link}

measure method
==============

::: {.section .multi-line-signature}
[PerformanceMeasure](../performancemeasure-class)? measure(

1.  [String](../../dart-core/string-class) measureName,
2.  \[dynamic measureOptions\_OR\_startMark,
3.  [String](../../dart-core/string-class)? endMark\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
PerformanceMeasure? measure(String measureName,
    [measureOptions_OR_startMark, String? endMark]) {
  if (measureOptions_OR_startMark == null && endMark == null) {
    return _measure_1(measureName);
  }
  if ((measureOptions_OR_startMark is String ||
          measureOptions_OR_startMark == null) &&
      endMark == null) {
    return _measure_2(measureName, measureOptions_OR_startMark);
  }
  if ((measureOptions_OR_startMark is String ||
      measureOptions_OR_startMark == null)) {
    return _measure_3(measureName, measureOptions_OR_startMark, endMark);
  }
  if ((measureOptions_OR_startMark is Map) && endMark == null) {
    var measureOptions_1 =
        convertDartToNative_Dictionary(measureOptions_OR_startMark);
    return _measure_4(measureName, measureOptions_1);
  }
  throw new ArgumentError("Incorrect number or type of arguments");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Performance/measure.html>
:::
