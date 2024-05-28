[dart:html](../../dart-html/dart-html-library){._links-link}

MediaStreamTrackEvent constructor
=================================

::: {.section .multi-line-signature}
MediaStreamTrackEvent(

1.  [String](../../dart-core/string-class) type,
2.  [Map](../../dart-core/map-class) eventInitDict

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory MediaStreamTrackEvent(String type, Map eventInitDict) {
  var eventInitDict_1 = convertDartToNative_Dictionary(eventInitDict);
  return MediaStreamTrackEvent._create_1(type, eventInitDict_1);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/MediaStreamTrackEvent/MediaStreamTrackEvent.html>
:::
