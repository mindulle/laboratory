[dart:html](../../dart-html/dart-html-library){._links-link}

MediaRecorder constructor
=========================

::: {.section .multi-line-signature}
MediaRecorder(

1.  [MediaStream](../mediastream-class) stream,
2.  \[[Map](../../dart-core/map-class)? options\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory MediaRecorder(MediaStream stream, [Map? options]) {
  if (options != null) {
    var options_1 = convertDartToNative_Dictionary(options);
    return MediaRecorder._create_1(stream, options_1);
  }
  return MediaRecorder._create_2(stream);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/MediaRecorder/MediaRecorder.html>
:::
