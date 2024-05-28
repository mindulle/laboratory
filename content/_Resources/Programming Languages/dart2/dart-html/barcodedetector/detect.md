[dart:html](../../dart-html/dart-html-library){._links-link}

detect method
=============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[List](../../dart-core/list-class)\>
detect(

1.  dynamic image

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<List<dynamic>> detect(/*ImageBitmapSource*/ image) =>
    promiseToFuture<List<dynamic>>(JS("", "#.detect(#)", this, image));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/BarcodeDetector/detect.html>
:::
