[dart:convert](../../dart-convert/dart-convert-library){._links-link}

convert method
==============

::: {.section .multi-line-signature}
[Uint8List](../../dart-typed_data/uint8list-class) convert(

1.  [String](../../dart-core/string-class) input,
2.  \[[int](../../dart-core/int-class) start = 0,
3.  [int](../../dart-core/int-class)? end\]

)

::: {.features}
override
:::
:::

Decodes the characters of `input` from `start` to `end` as base64.

If `start` is omitted, it defaults to the start of `input`. If `end` is
omitted, it defaults to the end of `input`.

The returned [Uint8List](../../dart-typed_data/uint8list-class) contains
exactly the decoded bytes, so the
[Uint8List.length](../../dart-core/list/length) is precisely the number
of decoded bytes. The
[Uint8List.buffer](../../dart-typed_data/typeddata/buffer) may be larger
than the decoded bytes.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Uint8List convert(String input, [int start = 0, int? end]) {
  end = RangeError.checkValidRange(start, end, input.length);
  if (start == end) return Uint8List(0);
  var decoder = _Base64Decoder();
  var buffer = decoder.decode(input, start, end)!;
  decoder.close(input, end);
  return buffer;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/Base64Decoder/convert.html>
:::
