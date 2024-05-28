[dart:html](../../dart-html/dart-html-library){._links-link}

enumerateDevices method
=======================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[List](../../dart-core/list-class)\>
enumerateDevices()
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<List<dynamic>> enumerateDevices() =>
    promiseToFuture<List<dynamic>>(JS("", "#.enumerateDevices()", this));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/MediaDevices/enumerateDevices.html>
:::
