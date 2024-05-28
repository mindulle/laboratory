[dart:indexed\_db](../../dart-indexed_db/dart-indexed_db-library){._links-link}

Observer constructor
====================

::: {.section .multi-line-signature}
Observer(

1.  [ObserverCallback](../observercallback) callback

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Observer(ObserverCallback callback) {
  var callback_1 = convertDartClosureToJS(callback, 1);
  return Observer._create_1(callback_1);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-indexed_db/Observer/Observer.html>
:::
