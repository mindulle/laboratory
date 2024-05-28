[dart:convert](../../dart-convert/dart-convert-library){._links-link}

decode method
=============

::: {.section .multi-line-signature}
[String](../../dart-core/string-class) decode(

1.  [List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>
    bytes,
2.  {[bool](../../dart-core/bool-class)? allowInvalid}

)

::: {.features}
override
:::
:::

Decodes the Latin-1 `bytes` (a list of unsigned 8-bit integers) to the
corresponding string.

If `bytes` contains values that are not in the range 0 .. 255, the
decoder will eventually throw a
[FormatException](../../dart-core/formatexception-class).

If `allowInvalid` is not provided, it defaults to the value used to
create this [Latin1Codec](../latin1codec-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String decode(List<int> bytes, {bool? allowInvalid}) {
  if (allowInvalid ?? _allowInvalid) {
    return const Latin1Decoder(allowInvalid: true).convert(bytes);
  } else {
    return const Latin1Decoder(allowInvalid: false).convert(bytes);
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/Latin1Codec/decode.html>
:::
