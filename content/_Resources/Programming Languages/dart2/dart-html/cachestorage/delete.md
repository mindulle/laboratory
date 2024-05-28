[dart:html](../../dart-html/dart-html-library){._links-link}

delete method
=============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) delete(

1.  [String](../../dart-core/string-class) cacheName

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future delete(String cacheName) =>
    promiseToFuture(JS("", "#.delete(#)", this, cacheName));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CacheStorage/delete.html>
:::
