[dart:html](../../dart-html/dart-html-library){._links-link}

MediaStream constructor
=======================

::: {.section .multi-line-signature}
MediaStream(

1.  \[dynamic stream\_OR\_tracks\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory MediaStream([stream_OR_tracks]) {
  if (stream_OR_tracks == null) {
    return MediaStream._create_1();
  }
  if ((stream_OR_tracks is MediaStream)) {
    return MediaStream._create_2(stream_OR_tracks);
  }
  if ((stream_OR_tracks is List<MediaStreamTrack>)) {
    return MediaStream._create_3(stream_OR_tracks);
  }
  throw new ArgumentError("Incorrect number or type of arguments");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/MediaStream/MediaStream.html>
:::
