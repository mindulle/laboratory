[dart:html](../../dart-html/dart-html-library){._links-link}

TrackDefault constructor
========================

::: {.section .multi-line-signature}
TrackDefault(

1.  [String](../../dart-core/string-class) type,
2.  [String](../../dart-core/string-class) language,
3.  [String](../../dart-core/string-class) label,
4.  [List](../../dart-core/list-class)\<[String](../../dart-core/string-class)\>
    kinds,
5.  \[[String](../../dart-core/string-class)? byteStreamTrackID\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory TrackDefault(
    String type, String language, String label, List<String> kinds,
    [String? byteStreamTrackID]) {
  if (byteStreamTrackID != null) {
    List kinds_1 = convertDartToNative_StringArray(kinds);
    return TrackDefault._create_1(
        type, language, label, kinds_1, byteStreamTrackID);
  }
  List kinds_1 = convertDartToNative_StringArray(kinds);
  return TrackDefault._create_2(type, language, label, kinds_1);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/TrackDefault/TrackDefault.html>
:::
