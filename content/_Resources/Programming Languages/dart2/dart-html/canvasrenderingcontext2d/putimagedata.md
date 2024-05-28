[dart:html](../../dart-html/dart-html-library){._links-link}

putImageData method
===================

::: {.section .multi-line-signature}
void putImageData(

1.  [ImageData](../imagedata-class) imagedata,
2.  [int](../../dart-core/int-class) dx,
3.  [int](../../dart-core/int-class) dy,
4.  \[[int](../../dart-core/int-class)? dirtyX,
5.  [int](../../dart-core/int-class)? dirtyY,
6.  [int](../../dart-core/int-class)? dirtyWidth,
7.  [int](../../dart-core/int-class)? dirtyHeight\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void putImageData(ImageData imagedata, int dx, int dy,
    [int? dirtyX, int? dirtyY, int? dirtyWidth, int? dirtyHeight]) {
  if (dirtyX == null &&
      dirtyY == null &&
      dirtyWidth == null &&
      dirtyHeight == null) {
    var imagedata_1 = convertDartToNative_ImageData(imagedata);
    _putImageData_1(imagedata_1, dx, dy);
    return;
  }
  if (dirtyHeight != null &&
      dirtyWidth != null &&
      dirtyY != null &&
      dirtyX != null) {
    var imagedata_1 = convertDartToNative_ImageData(imagedata);
    _putImageData_2(
        imagedata_1, dx, dy, dirtyX, dirtyY, dirtyWidth, dirtyHeight);
    return;
  }
  throw new ArgumentError("Incorrect number or type of arguments");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CanvasRenderingContext2D/putImageData.html>
:::
