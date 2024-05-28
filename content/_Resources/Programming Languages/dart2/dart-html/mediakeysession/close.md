[dart:html](../../dart-html/dart-html-library){._links-link}

close method
============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) close()
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future close() => promiseToFuture(JS("", "#.close()", this));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/MediaKeySession/close.html>
:::
