[dart:html](../../dart-html/dart-html-library){._links-link}

observe method
==============

::: {.section .multi-line-signature}
void observe(

1.  [Map](../../dart-core/map-class) options

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void observe(Map options) {
  var options_1 = convertDartToNative_Dictionary(options);
  _observe_1(options_1);
  return;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/PerformanceObserver/observe.html>
:::
