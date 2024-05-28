[dart:html](../../dart-html/dart-html-library){._links-link}

open method
===========

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) open(

1.  [String](../../dart-core/string-class) cacheName

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future open(String cacheName) =>
    promiseToFuture(JS("creates:_Cache;", "#.open(#)", this, cacheName));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CacheStorage/open.html>
:::
