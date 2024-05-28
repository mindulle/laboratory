[dart:html](../../dart-html/dart-html-library){._links-link}

getNotifications method
=======================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[List](../../dart-core/list-class)\>
getNotifications(

1.  \[[Map](../../dart-core/map-class)? filter\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<List<dynamic>> getNotifications([Map? filter]) {
  var filter_dict = null;
  if (filter != null) {
    filter_dict = convertDartToNative_Dictionary(filter);
  }
  return promiseToFuture<List<dynamic>>(
      JS("", "#.getNotifications(#)", this, filter_dict));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/ServiceWorkerRegistration/getNotifications.html>
:::
