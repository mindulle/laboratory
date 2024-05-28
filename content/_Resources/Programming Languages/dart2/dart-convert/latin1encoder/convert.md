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
inherited
:::
:::

Converts the [String](../../dart-core/string-class) into a list of its
code units.

If `start` and `end` are provided, only the substring
`string.substring(start, end)` is used as input to the conversion.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Uint8List convert(String string, [int start = 0, int? end]) {
  var stringLength = string.length;
  end = RangeError.checkValidRange(start, end, stringLength);
  var length = end - start;
  var result = Uint8List(length);
  for (var i = 0; i < length; i++) {
    var codeUnit = string.codeUnitAt(start + i);
    if ((codeUnit & ~_subsetMask) != 0) {
      throw ArgumentError.value(
          string, "string", "Contains invalid characters.");
    }
    result[i] = codeUnit;
  }
  return result;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/Latin1Encoder/convert.html>
:::
