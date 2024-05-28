[dart:core](../../dart-core/dart-core-library){._links-link}

UriData.fromBytes constructor
=============================

::: {.section .multi-line-signature}
UriData.fromBytes(

1.  [List](../list-class)\<[int](../int-class)\> bytes,
2.  {[String](../string-class) mimeType = \"application/octet-stream\",
3.  [Map](../map-class)\<[String](../string-class),
    [String](../string-class)\>? parameters,
4.  [bool](../bool-class) percentEncoded = false}

)
:::

Creates a `data:` URI containing an encoding of `bytes`.

Equivalent to `Uri.dataFromBytes(...).data`, but may be more efficient
if the [uri](uri) itself isn\'t used.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory UriData.fromBytes(List<int> bytes,
    {String mimeType = "application/octet-stream",
    Map<String, String>? parameters,
    bool percentEncoded = false}) {
  StringBuffer buffer = StringBuffer();
  List<int> indices = [_noScheme];
  _writeUri(mimeType, null, parameters, buffer, indices);
  indices.add(buffer.length);
  if (percentEncoded) {
    buffer.write(',');
    _uriEncodeBytes(_uricTable, bytes, buffer);
  } else {
    buffer.write(';base64,');
    indices.add(buffer.length - 1);
    _base64.encoder
        .startChunkedConversion(StringConversionSink.fromStringSink(buffer))
        .addSlice(bytes, 0, bytes.length, true);
  }

  return UriData._(buffer.toString(), indices, null);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/UriData/UriData.fromBytes.html>
:::
