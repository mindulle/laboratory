[dart:indexed\_db](../../dart-indexed_db/dart-indexed_db-library){._links-link}

count method
============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[int](../../dart-core/int-class)\>
count(

1.  \[dynamic key\_OR\_range\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<int> count([key_OR_range]) {
  try {
    var request = _count(key_OR_range);
    return _completeRequest(request);
  } catch (e, stacktrace) {
    return new Future.error(e, stacktrace);
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-indexed_db/ObjectStore/count.html>
:::
