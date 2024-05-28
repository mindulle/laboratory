[dart:html](../../dart-html/dart-html-library){._links-link}

FaceDetector constructor
========================

::: {.section .multi-line-signature}
FaceDetector(

1.  \[[Map](../../dart-core/map-class)? faceDetectorOptions\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory FaceDetector([Map? faceDetectorOptions]) {
  if (faceDetectorOptions != null) {
    var faceDetectorOptions_1 =
        convertDartToNative_Dictionary(faceDetectorOptions);
    return FaceDetector._create_1(faceDetectorOptions_1);
  }
  return FaceDetector._create_2();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/FaceDetector/FaceDetector.html>
:::
