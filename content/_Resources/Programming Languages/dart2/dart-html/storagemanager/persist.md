[dart:html](../../dart-html/dart-html-library){._links-link}

persist method
==============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[bool](../../dart-core/bool-class)\>
persist()
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<bool> persist() => promiseToFuture<bool>(JS("", "#.persist()", this));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/StorageManager/persist.html>
:::
