[dart:convert](../../dart-convert/dart-convert-library){._links-link}

convert method
==============

::: {.section .multi-line-signature}
[List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>
convert(

1.  [Object](../../dart-core/object-class)? object

)

::: {.features}
override
:::
:::

Convert `object` into UTF-8 encoded JSON.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
List<int> convert(Object? object) {
  var bytes = <List<int>>[];
  // The `stringify` function always converts into chunks.
  // Collect the chunks into the `bytes` list, then combine them afterwards.
  void addChunk(Uint8List chunk, int start, int end) {
    if (start > 0 || end < chunk.length) {
      var length = end - start;
      chunk =
          Uint8List.view(chunk.buffer, chunk.offsetInBytes + start, length);
    }
    bytes.add(chunk);
  }

  _JsonUtf8Stringifier.stringify(
      object, _indent, _toEncodable, _bufferSize, addChunk);
  if (bytes.length == 1) return bytes[0];
  var length = 0;
  for (var i = 0; i < bytes.length; i++) {
    length += bytes[i].length;
  }
  var result = Uint8List(length);
  for (var i = 0, offset = 0; i < bytes.length; i++) {
    var byteList = bytes[i];
    int end = offset + byteList.length;
    result.setRange(offset, end, byteList);
    offset = end;
  }
  return result;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/JsonUtf8Encoder/convert.html>
:::
