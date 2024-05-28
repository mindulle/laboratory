[dart:core](../../dart-core/dart-core-library){._links-link}

UriData.fromString constructor
==============================

::: {.section .multi-line-signature}
UriData.fromString(

1.  [String](../string-class) content,
2.  {[String](../string-class)? mimeType,
3.  [Encoding](../../dart-convert/encoding-class)? encoding,
4.  [Map](../map-class)\<[String](../string-class),
    [String](../string-class)\>? parameters,
5.  [bool](../bool-class) base64 = false}

)
:::

Creates a `data:` URI containing the `content` string.

Equivalent to `Uri.dataFromString(...).data`, but may be more efficient
if the [uri](uri) itself isn\'t used.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory UriData.fromString(String content,
    {String? mimeType,
    Encoding? encoding,
    Map<String, String>? parameters,
    bool base64 = false}) {
  StringBuffer buffer = StringBuffer();
  List<int> indices = [_noScheme];
  String? charsetName = parameters?["charset"];
  String? encodingName;
  if (encoding == null) {
    if (charsetName != null) {
      encoding = Encoding.getByName(charsetName);
    }
  } else if (charsetName == null) {
    // Non-null only if parameters does not contain "charset".
    encodingName = encoding.name;
  }
  encoding ??= ascii;
  _writeUri(mimeType, encodingName, parameters, buffer, indices);
  indices.add(buffer.length);
  if (base64) {
    buffer.write(';base64,');
    indices.add(buffer.length - 1);
    buffer.write(encoding.fuse(_base64).encode(content));
  } else {
    buffer.write(',');
    _uriEncodeBytes(_uricTable, encoding.encode(content), buffer);
  }
  return UriData._(buffer.toString(), indices, null);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/UriData/UriData.fromString.html>
:::
