[dart:convert](../../dart-convert/dart-convert-library){._links-link}

decodeStream method
===================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[String](../../dart-core/string-class)\>
decodeStream(

1.  [Stream](../../dart-async/stream-class)\<[List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>\>
    byteStream

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<String> decodeStream(Stream<List<int>> byteStream) {
  return decoder
      .bind(byteStream)
      .fold(StringBuffer(),
          (StringBuffer buffer, String string) => buffer..write(string))
      .then((StringBuffer buffer) => buffer.toString());
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/Encoding/decodeStream.html>
:::
