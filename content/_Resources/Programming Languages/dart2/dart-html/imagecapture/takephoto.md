[dart:html](../../dart-html/dart-html-library){._links-link}

takePhoto method
================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[Blob](../blob-class)\>
takePhoto(

1.  \[[Map](../../dart-core/map-class)? photoSettings\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<Blob> takePhoto([Map? photoSettings]) {
  var photoSettings_dict = null;
  if (photoSettings != null) {
    photoSettings_dict = convertDartToNative_Dictionary(photoSettings);
  }
  return promiseToFuture<Blob>(
      JS("creates:Blob;", "#.takePhoto(#)", this, photoSettings_dict));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/ImageCapture/takePhoto.html>
:::
