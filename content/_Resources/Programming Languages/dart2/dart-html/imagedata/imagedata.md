[dart:html](../../dart-html/dart-html-library){._links-link}

ImageData constructor
=====================

::: {.section .multi-line-signature}
ImageData(

1.  dynamic data\_OR\_sw,
2.  [int](../../dart-core/int-class) sh\_OR\_sw,
3.  \[[int](../../dart-core/int-class)? sh\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory ImageData(data_OR_sw, int sh_OR_sw, [int? sh]) {
  if ((sh_OR_sw is int) && (data_OR_sw is int) && sh == null) {
    return ImageData._create_1(data_OR_sw, sh_OR_sw);
  }
  if ((sh_OR_sw is int) && (data_OR_sw is Uint8ClampedList) && sh == null) {
    return ImageData._create_2(data_OR_sw, sh_OR_sw);
  }
  if ((sh is int) && (sh_OR_sw is int) && (data_OR_sw is Uint8ClampedList)) {
    return ImageData._create_3(data_OR_sw, sh_OR_sw, sh);
  }
  throw new ArgumentError("Incorrect number or type of arguments");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/ImageData/ImageData.html>
:::
