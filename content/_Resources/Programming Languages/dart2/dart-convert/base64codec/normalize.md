[dart:convert](../../dart-convert/dart-convert-library){._links-link}

normalize method
================

::: {.section .multi-line-signature}
[String](../../dart-core/string-class) normalize(

1.  [String](../../dart-core/string-class) source,
2.  \[[int](../../dart-core/int-class) start = 0,
3.  [int](../../dart-core/int-class)? end\]

)
:::

Validates and normalizes the base64 encoded data in `source`.

Only acts on the substring from `start` to `end`, with `end` defaulting
to the end of the string.

Normalization will:

-   Unescape any `%`-escapes.
-   Only allow valid characters (`A`-`Z`, `a`-`z`, `0`-`9`, `/` and
    `+`).
-   Normalize a `_` or `-` character to `/` or `+`.
-   Validate that existing padding (trailing `=` characters) is correct.
-   If no padding exists, add correct padding if necessary and possible.
-   Validate that the length is correct (a multiple of four).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String normalize(String source, [int start = 0, int? end]) {
  end = RangeError.checkValidRange(start, end, source.length);
  const percent = 0x25;
  const equals = 0x3d;
  StringBuffer? buffer;
  var sliceStart = start;
  var alphabet = _Base64Encoder._base64Alphabet;
  var inverseAlphabet = _Base64Decoder._inverseAlphabet;
  var firstPadding = -1;
  var firstPaddingSourceIndex = -1;
  var paddingCount = 0;
  for (var i = start; i < end;) {
    var sliceEnd = i;
    var char = source.codeUnitAt(i++);
    var originalChar = char;
    // Normalize char, keep originalChar to see if it matches the source.
    if (char == percent) {
      if (i + 2 <= end) {
        char = parseHexByte(source, i); // May be negative.
        i += 2;
        // We know that %25 isn't valid, but our table considers it
        // a potential padding start, so skip the checks.
        if (char == percent) char = -1;
      } else {
        // An invalid HEX escape (too short).
        // Just skip past the handling and reach the throw below.
        char = -1;
      }
    }
    // If char is negative here, hex-decoding failed in some way.
    if (0 <= char && char <= 127) {
      var value = inverseAlphabet[char];
      if (value >= 0) {
        char = alphabet.codeUnitAt(value);
        if (char == originalChar) continue;
      } else if (value == _Base64Decoder._padding) {
        // We have ruled out percent, so char is '='.
        if (firstPadding < 0) {
          // Mark position in normalized output where padding occurs.
          firstPadding = (buffer?.length ?? 0) + (sliceEnd - sliceStart);
          firstPaddingSourceIndex = sliceEnd;
        }
        paddingCount++;
        // It could have been an escaped equals (%3D).
        if (originalChar == equals) continue;
      }
      if (value != _Base64Decoder._invalid) {
        (buffer ??= StringBuffer())
          ..write(source.substring(sliceStart, sliceEnd))
          ..writeCharCode(char);
        sliceStart = i;
        continue;
      }
    }
    throw FormatException("Invalid base64 data", source, sliceEnd);
  }
  if (buffer != null) {
    buffer.write(source.substring(sliceStart, end));
    if (firstPadding >= 0) {
      // There was padding in the source. Check that it is valid:
      // * result length a multiple of four
      // * one or two padding characters at the end.
      _checkPadding(source, firstPaddingSourceIndex, end, firstPadding,
          paddingCount, buffer.length);
    } else {
      // Length of last chunk (1-4 chars) in the encoding.
      var endLength = ((buffer.length - 1) % 4) + 1;
      if (endLength == 1) {
        // The data must have length 0, 2 or 3 modulo 4.
        throw FormatException("Invalid base64 encoding length ", source, end);
      }
      while (endLength < 4) {
        buffer.write("=");
        endLength++;
      }
    }
    return source.replaceRange(start, end, buffer.toString());
  }
  // Original was already normalized, only check padding.
  var length = end - start;
  if (firstPadding >= 0) {
    _checkPadding(source, firstPaddingSourceIndex, end, firstPadding,
        paddingCount, length);
  } else {
    // No padding given, so add some if needed it.
    var endLength = length % 4;
    if (endLength == 1) {
      // The data must have length 0, 2 or 3 modulo 4.
      throw FormatException("Invalid base64 encoding length ", source, end);
    }
    if (endLength > 1) {
      // There is no "insertAt" on String, but this works as well.
      source = source.replaceRange(end, end, (endLength == 2) ? "==" : "=");
    }
  }
  return source;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/Base64Codec/normalize.html>
:::
