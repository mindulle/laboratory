[dart:convert](../../dart-convert/dart-convert-library){._links-link}

convert method
==============

::: {.section .multi-line-signature}
[Uint8List](../../dart-typed_data/uint8list-class) convert(

1.  [String](../../dart-core/string-class) string,
2.  \[[int](../../dart-core/int-class) start = 0,
3.  [int](../../dart-core/int-class)? end\]

)

::: {.features}
override
:::
:::

Converts `string` to its UTF-8 code units (a list of unsigned 8-bit
integers).

If `start` and `end` are provided, only the substring
`string.substring(start, end)` is converted.

Any unpaired surrogate character (`U+D800`-`U+DFFF`) in the input string
is encoded as a Unicode Replacement character `U+FFFD` (�).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Uint8List convert(String string, [int start = 0, int? end]) {
  var stringLength = string.length;
  end = RangeError.checkValidRange(start, end, stringLength);
  var length = end - start;
  if (length == 0) return Uint8List(0);
  // Create a new encoder with a length that is guaranteed to be big enough.
  // A single code unit uses at most 3 bytes, a surrogate pair at most 4.
  var encoder = _Utf8Encoder.withBufferSize(length * 3);
  var endPosition = encoder._fillBuffer(string, start, end);
  assert(endPosition >= end - 1);
  if (endPosition != end) {
    // Encoding skipped the last code unit.
    // That can only happen if the last code unit is a leadsurrogate.
    // Force encoding of the lead surrogate by itself.
    var lastCodeUnit = string.codeUnitAt(end - 1);
    assert(_isLeadSurrogate(lastCodeUnit));
    // Write a replacement character to represent the unpaired surrogate.
    encoder._writeReplacementCharacter();
  }
  return encoder._buffer.sublist(0, encoder._bufferIndex);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/Utf8Encoder/convert.html>
:::
