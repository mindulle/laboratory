[dart:indexed\_db](../../dart-indexed_db/dart-indexed_db-library){._links-link}

getObject method
================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) getObject(

1.  dynamic key

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future getObject(key) {
  try {
    var request = _get(key);

    return _completeRequest(request);
  } catch (e, stacktrace) {
    return new Future.error(e, stacktrace);
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-indexed_db/ObjectStore/getObject.html>
:::
