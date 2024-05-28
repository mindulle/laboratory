[dart:html](../../dart-html/dart-html-library){._links-link}

createImageData method
======================

::: {.section .multi-line-signature}
<div>

1.  \@Creates(\'ImageData\|=Object\')

</div>

[ImageData](../imagedata-class) createImageData(

1.  dynamic data\_OR\_imagedata\_OR\_sw,
2.  \[[int](../../dart-core/int-class)? sh\_OR\_sw,
3.  dynamic imageDataColorSettings\_OR\_sh,
4.  [Map](../../dart-core/map-class)? imageDataColorSettings\]

)

::: {.features}
\@Creates(\'ImageData\|=Object\')
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Creates('ImageData|=Object')
ImageData createImageData(data_OR_imagedata_OR_sw,
    [int? sh_OR_sw,
    imageDataColorSettings_OR_sh,
    Map? imageDataColorSettings]) {
  if ((data_OR_imagedata_OR_sw is ImageData) &&
      sh_OR_sw == null &&
      imageDataColorSettings_OR_sh == null &&
      imageDataColorSettings == null) {
    var imagedata_1 = convertDartToNative_ImageData(data_OR_imagedata_OR_sw);
    return convertNativeToDart_ImageData(_createImageData_1(imagedata_1));
  }
  if (sh_OR_sw != null &&
      (data_OR_imagedata_OR_sw is int) &&
      imageDataColorSettings_OR_sh == null &&
      imageDataColorSettings == null) {
    return convertNativeToDart_ImageData(
        _createImageData_2(data_OR_imagedata_OR_sw, sh_OR_sw));
  }
  if ((imageDataColorSettings_OR_sh is Map) &&
      sh_OR_sw != null &&
      (data_OR_imagedata_OR_sw is int) &&
      imageDataColorSettings == null) {
    var imageDataColorSettings_1 =
        convertDartToNative_Dictionary(imageDataColorSettings_OR_sh);
    return convertNativeToDart_ImageData(_createImageData_3(
        data_OR_imagedata_OR_sw, sh_OR_sw, imageDataColorSettings_1));
  }
  if ((imageDataColorSettings_OR_sh is int) &&
      sh_OR_sw != null &&
      data_OR_imagedata_OR_sw != null &&
      imageDataColorSettings == null) {
    return convertNativeToDart_ImageData(_createImageData_4(
        data_OR_imagedata_OR_sw, sh_OR_sw, imageDataColorSettings_OR_sh));
  }
  if (imageDataColorSettings != null &&
      (imageDataColorSettings_OR_sh is int) &&
      sh_OR_sw != null &&
      data_OR_imagedata_OR_sw != null) {
    var imageDataColorSettings_1 =
        convertDartToNative_Dictionary(imageDataColorSettings);
    return convertNativeToDart_ImageData(_createImageData_5(
        data_OR_imagedata_OR_sw,
        sh_OR_sw,
        imageDataColorSettings_OR_sh,
        imageDataColorSettings_1));
  }
  throw new ArgumentError("Incorrect number or type of arguments");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CanvasRenderingContext2D/createImageData.html>
:::
