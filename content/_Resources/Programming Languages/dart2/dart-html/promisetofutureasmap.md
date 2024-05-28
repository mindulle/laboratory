[dart:html](../dart-html/dart-html-library){._links-link}

promiseToFutureAsMap function
=============================

::: {.section .multi-line-signature}
[Future](../dart-async/future-class)\<[Map](../dart-core/map-class)\<[String](../dart-core/string-class),
dynamic\>?\> promiseToFutureAsMap(

1.  dynamic jsPromise

)
:::

Convert a JS Promise to a Future\<Map\<String, dynamic\>\>.

On a successful result the native JS result will be converted to a Dart
Map. See `convertNativeToDart_Dictionary`. On a rejected promise the
error is forwarded without change.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<Map<String, dynamic>?> promiseToFutureAsMap(jsPromise) =>
    promiseToFuture(jsPromise).then(convertNativeToDart_Dictionary);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/promiseToFutureAsMap.html>
:::
