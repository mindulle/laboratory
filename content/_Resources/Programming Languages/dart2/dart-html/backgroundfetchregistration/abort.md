[dart:html](../../dart-html/dart-html-library){._links-link}

abort method
============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[bool](../../dart-core/bool-class)\>
abort()
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<bool> abort() => promiseToFuture<bool>(JS("", "#.abort()", this));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/BackgroundFetchRegistration/abort.html>
:::
