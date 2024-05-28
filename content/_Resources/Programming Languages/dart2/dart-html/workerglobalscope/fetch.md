[dart:html](../../dart-html/dart-html-library){._links-link}

fetch method
============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) fetch(

1.  dynamic input,
2.  \[[Map](../../dart-core/map-class)? init\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future fetch(/*RequestInfo*/ input, [Map? init]) {
  var init_dict = null;
  if (init != null) {
    init_dict = convertDartToNative_Dictionary(init);
  }
  return promiseToFuture(
      JS("creates:_Response;", "#.fetch(#, #)", this, input, init_dict));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/WorkerGlobalScope/fetch.html>
:::
