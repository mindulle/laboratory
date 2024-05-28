[dart:html](../../dart-html/dart-html-library){._links-link}

addStream method
================

::: {.section .multi-line-signature}
void addStream(

1.  [MediaStream](../mediastream-class)? stream,
2.  \[[Map](../../dart-core/map-class)? mediaConstraints\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void addStream(MediaStream? stream, [Map? mediaConstraints]) {
  if (mediaConstraints != null) {
    var mediaConstraints_1 = convertDartToNative_Dictionary(mediaConstraints);
    _addStream_1(stream, mediaConstraints_1);
    return;
  }
  _addStream_2(stream);
  return;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/RtcPeerConnection/addStream.html>
:::
