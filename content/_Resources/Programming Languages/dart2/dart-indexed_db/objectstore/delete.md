[dart:indexed\_db](../../dart-indexed_db/dart-indexed_db-library){._links-link}

delete method
=============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) delete(

1.  dynamic key\_OR\_keyRange

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future delete(key_OR_keyRange) {
  try {
    return _completeRequest(_delete(key_OR_keyRange));
  } catch (e, stacktrace) {
    return new Future.error(e, stacktrace);
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-indexed_db/ObjectStore/delete.html>
:::
