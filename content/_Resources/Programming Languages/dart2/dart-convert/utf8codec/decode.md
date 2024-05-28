[dart:convert](../../dart-convert/dart-convert-library){._links-link}

decode method
=============

::: {.section .multi-line-signature}
[String](../../dart-core/string-class) decode(

1.  [List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>
    codeUnits,
2.  {[bool](../../dart-core/bool-class)? allowMalformed}

)

::: {.features}
override
:::
:::

Decodes the UTF-8 `codeUnits` (a list of unsigned 8-bit integers) to the
corresponding string.

If the `codeUnits` start with the encoding of a
[unicodeBomCharacterRune](../unicodebomcharacterrune-constant), that
character is discarded.

If `allowMalformed` is `true`, the decoder replaces invalid (or
unterminated) character sequences with the Unicode Replacement character
`U+FFFD` (�). Otherwise it throws a
[FormatException](../../dart-core/formatexception-class).

If `allowMalformed` is not given, it defaults to the `allowMalformed`
that was used to instantiate `this`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String decode(List<int> codeUnits, {bool? allowMalformed}) {
  // Switch between const objects to avoid allocation.
  Utf8Decoder decoder = allowMalformed ?? _allowMalformed
      ? const Utf8Decoder(allowMalformed: true)
      : const Utf8Decoder(allowMalformed: false);
  return decoder.convert(codeUnits);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/Utf8Codec/decode.html>
:::
