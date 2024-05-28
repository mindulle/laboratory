[dart:html](../../dart-html/dart-html-library){._links-link}

MediaMetadata constructor
=========================

::: {.section .multi-line-signature}
MediaMetadata(

1.  \[[Map](../../dart-core/map-class)? metadata\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory MediaMetadata([Map? metadata]) {
  if (metadata != null) {
    var metadata_1 = convertDartToNative_Dictionary(metadata);
    return MediaMetadata._create_1(metadata_1);
  }
  return MediaMetadata._create_2();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/MediaMetadata/MediaMetadata.html>
:::
