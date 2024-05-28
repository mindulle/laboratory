[dart:convert](../../dart-convert/dart-convert-library){._links-link}

convert method
==============

::: {.section .multi-line-signature}
[String](../../dart-core/string-class) convert(

1.  [List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>
    codeUnits,
2.  \[[int](../../dart-core/int-class) start = 0,
3.  [int](../../dart-core/int-class)? end\]

)

::: {.features}
override
:::
:::

Converts the UTF-8 `codeUnits` (a list of unsigned 8-bit integers) to
the corresponding string.

Uses the code units from `start` to, but not including, `end`. If `end`
is omitted, it defaults to `codeUnits.length`.

If the `codeUnits` start with the encoding of a
[unicodeBomCharacterRune](../unicodebomcharacterrune-constant), that
character is discarded.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String convert(List<int> codeUnits, [int start = 0, int? end]) {
  // Allow the implementation to intercept and specialize based on the type
  // of codeUnits.
  var result = _convertIntercepted(_allowMalformed, codeUnits, start, end);
  if (result != null) {
    return result;
  }

  return _Utf8Decoder(_allowMalformed).convertSingle(codeUnits, start, end);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/Utf8Decoder/convert.html>
:::
