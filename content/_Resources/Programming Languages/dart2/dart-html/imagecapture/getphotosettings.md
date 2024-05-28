[dart:html](../../dart-html/dart-html-library){._links-link}

getPhotoSettings method
=======================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[Map](../../dart-core/map-class)\<[String](../../dart-core/string-class),
dynamic\>?\> getPhotoSettings()
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<Map<String, dynamic>?> getPhotoSettings() =>
    promiseToFutureAsMap(JS("", "#.getPhotoSettings()", this));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/ImageCapture/getPhotoSettings.html>
:::
