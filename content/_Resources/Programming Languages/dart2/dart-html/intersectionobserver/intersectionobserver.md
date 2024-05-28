[dart:html](../../dart-html/dart-html-library){._links-link}

IntersectionObserver constructor
================================

::: {.section .multi-line-signature}
IntersectionObserver(

1.  [IntersectionObserverCallback](../intersectionobservercallback)
    callback,
2.  \[[Map](../../dart-core/map-class)? options\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory IntersectionObserver(IntersectionObserverCallback callback,
    [Map? options]) {
  if (options != null) {
    var callback_1 = convertDartClosureToJS(callback, 2);
    var options_2 = convertDartToNative_Dictionary(options);
    return IntersectionObserver._create_1(callback_1, options_2);
  }
  var callback_1 = convertDartClosureToJS(callback, 2);
  return IntersectionObserver._create_2(callback_1);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/IntersectionObserver/IntersectionObserver.html>
:::
