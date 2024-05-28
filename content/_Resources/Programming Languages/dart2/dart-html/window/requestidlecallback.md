[dart:html](../../dart-html/dart-html-library){._links-link}

requestIdleCallback method
==========================

::: {.section .multi-line-signature}
[int](../../dart-core/int-class) requestIdleCallback(

1.  [IdleRequestCallback](../idlerequestcallback) callback,
2.  \[[Map](../../dart-core/map-class)? options\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int requestIdleCallback(IdleRequestCallback callback, [Map? options]) {
  if (options != null) {
    var callback_1 = convertDartClosureToJS(callback, 1);
    var options_2 = convertDartToNative_Dictionary(options);
    return _requestIdleCallback_1(callback_1, options_2);
  }
  var callback_1 = convertDartClosureToJS(callback, 1);
  return _requestIdleCallback_2(callback_1);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Window/requestIdleCallback.html>
:::
