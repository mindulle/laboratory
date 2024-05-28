[dart:html](../../dart-html/dart-html-library){._links-link}

enable method
=============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) enable()
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future enable() => promiseToFuture(JS("", "#.enable()", this));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/NavigationPreloadManager/enable.html>
:::
