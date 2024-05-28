[dart:html](../../dart-html/dart-html-library){._links-link}

load method
===========

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) load(

1.  [String](../../dart-core/string-class) sessionId

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future load(String sessionId) =>
    promiseToFuture(JS("", "#.load(#)", this, sessionId));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/MediaKeySession/load.html>
:::
