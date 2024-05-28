[dart:html](../../dart-html/dart-html-library){._links-link}

ResizeObserver constructor
==========================

::: {.section .multi-line-signature}
ResizeObserver(

1.  [ResizeObserverCallback](../resizeobservercallback) callback

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory ResizeObserver(ResizeObserverCallback callback) {
  var callback_1 = convertDartClosureToJS(callback, 2);
  return ResizeObserver._create_1(callback_1);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/ResizeObserver/ResizeObserver.html>
:::
