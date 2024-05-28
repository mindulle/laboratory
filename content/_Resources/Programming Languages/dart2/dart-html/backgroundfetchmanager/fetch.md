[dart:html](../../dart-html/dart-html-library){._links-link}

fetch method
============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[BackgroundFetchRegistration](../backgroundfetchregistration-class)\>
fetch(

1.  [String](../../dart-core/string-class) id,
2.  [Object](../../dart-core/object-class) requests,
3.  \[[Map](../../dart-core/map-class)? options\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<BackgroundFetchRegistration> fetch(String id, Object requests,
    [Map? options]) {
  var options_dict = null;
  if (options != null) {
    options_dict = convertDartToNative_Dictionary(options);
  }
  return promiseToFuture<BackgroundFetchRegistration>(JS(
      "creates:BackgroundFetchRegistration;",
      "#.fetch(#, #, #)",
      this,
      id,
      requests,
      options_dict));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/BackgroundFetchManager/fetch.html>
:::
