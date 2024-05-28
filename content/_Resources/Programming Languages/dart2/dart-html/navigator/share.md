[dart:html](../../dart-html/dart-html-library){._links-link}

share method
============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) share(

1.  \[[Map](../../dart-core/map-class)? data\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future share([Map? data]) {
  var data_dict = null;
  if (data != null) {
    data_dict = convertDartToNative_Dictionary(data);
  }
  return promiseToFuture(JS("", "#.share(#)", this, data_dict));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Navigator/share.html>
:::
