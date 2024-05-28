[dart:core](../../dart-core/dart-core-library){._links-link}

contentAsBytes method
=====================

::: {.section .multi-line-signature}
[Uint8List](../../dart-typed_data/uint8list-class) contentAsBytes()
:::

The content part of the data URI as bytes.

If the data is Base64 encoded, it will be decoded to bytes.

If the data is not Base64 encoded, it will be decoded by unescaping
percent-escaped characters and returning byte values of each unescaped
character. The bytes will not be, e.g., UTF-8 decoded.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Uint8List contentAsBytes() {
  String text = _text;
  int start = _separatorIndices.last + 1;
  if (isBase64) {
    return base64.decoder.convert(text, start);
  }

  // Not base64, do percent-decoding and return the remaining bytes.
  // Compute result size.
  const int percent = 0x25;
  int length = text.length - start;
  for (int i = start; i < text.length; i++) {
    var codeUnit = text.codeUnitAt(i);
    if (codeUnit == percent) {
      i += 2;
      length -= 2;
    }
  }
  // Fill result array.
  Uint8List result = Uint8List(length);
  if (length == text.length) {
    result.setRange(0, length, text.codeUnits, start);
    return result;
  }
  int index = 0;
  for (int i = start; i < text.length; i++) {
    var codeUnit = text.codeUnitAt(i);
    if (codeUnit != percent) {
      result[index++] = codeUnit;
    } else {
      if (i + 2 < text.length) {
        int byte = parseHexByte(text, i + 1);
        if (byte >= 0) {
          result[index++] = byte;
          i += 2;
          continue;
        }
      }
      throw FormatException("Invalid percent escape", text, i);
    }
  }
  assert(index == result.length);
  return result;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/UriData/contentAsBytes.html>
:::
