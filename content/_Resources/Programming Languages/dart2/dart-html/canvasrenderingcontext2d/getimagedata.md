[dart:html](../../dart-html/dart-html-library){._links-link}

getImageData method
===================

::: {.section .multi-line-signature}
<div>

1.  \@Creates(\'ImageData\|=Object\')

</div>

[ImageData](../imagedata-class) getImageData(

1.  [int](../../dart-core/int-class) sx,
2.  [int](../../dart-core/int-class) sy,
3.  [int](../../dart-core/int-class) sw,
4.  [int](../../dart-core/int-class) sh

)

::: {.features}
\@Creates(\'ImageData\|=Object\')
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Creates('ImageData|=Object')
ImageData getImageData(int sx, int sy, int sw, int sh) {
  return convertNativeToDart_ImageData(_getImageData_1(sx, sy, sw, sh));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CanvasRenderingContext2D/getImageData.html>
:::
