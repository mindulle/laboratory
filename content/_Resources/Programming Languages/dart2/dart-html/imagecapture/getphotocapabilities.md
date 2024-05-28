[dart:html](../../dart-html/dart-html-library){._links-link}

getPhotoCapabilities method
===========================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[PhotoCapabilities](../photocapabilities-class)\>
getPhotoCapabilities()
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<PhotoCapabilities> getPhotoCapabilities() =>
    promiseToFuture<PhotoCapabilities>(
        JS("creates:PhotoCapabilities;", "#.getPhotoCapabilities()", this));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/ImageCapture/getPhotoCapabilities.html>
:::
