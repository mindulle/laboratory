[dart:html](../../dart-html/dart-html-library){._links-link}

createImageDataFromImageData method
===================================

::: {.section .multi-line-signature}
[ImageData](../imagedata-class) createImageDataFromImageData(

1.  [ImageData](../imagedata-class) imagedata

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
ImageData createImageDataFromImageData(ImageData imagedata) =>
    JS('ImageData', '#.createImageData(#)', this, imagedata);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CanvasRenderingContext2D/createImageDataFromImageData.html>
:::
