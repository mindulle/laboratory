[dart:convert](../../dart-convert/dart-convert-library){._links-link}

convert method
==============

::: {.section .multi-line-signature}
[String](../../dart-core/string-class) convert(

1.  [List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>
    bytes,
2.  \[[int](../../dart-core/int-class) start = 0,
3.  [int](../../dart-core/int-class)? end\]

)

::: {.features}
inherited
:::
:::

Converts the `bytes` (a list of unsigned 7- or 8-bit integers) to the
corresponding string.

If `start` and `end` are provided, only the sub-list of bytes from
`start` to `end` (`end` not inclusive) is used as input to the
conversion.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String convert(List<int> bytes, [int start = 0, int? end]) {
  end = RangeError.checkValidRange(start, end, bytes.length);
  for (var i = start; i < end; i++) {
    var byte = bytes[i];
    if ((byte & ~_subsetMask) != 0) {
      if (!_allowInvalid) {
        throw FormatException("Invalid value in input: $byte");
      }
      return _convertInvalid(bytes, start, end);
    }
  }
  return String.fromCharCodes(bytes, start, end);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/AsciiDecoder/convert.html>
:::
