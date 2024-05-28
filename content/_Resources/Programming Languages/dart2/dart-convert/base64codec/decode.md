[dart:convert](../../dart-convert/dart-convert-library){._links-link}

decode method
=============

::: {.section .multi-line-signature}
[Uint8List](../../dart-typed_data/uint8list-class) decode(

1.  [String](../../dart-core/string-class) encoded

)

::: {.features}
override
:::
:::

Decodes `encoded`.

The input is decoded as if by `decoder.convert`.

The returned [Uint8List](../../dart-typed_data/uint8list-class) contains
exactly the decoded bytes, so the
[Uint8List.length](../../dart-core/list/length) is precisely the number
of decoded bytes. The
[Uint8List.buffer](../../dart-typed_data/typeddata/buffer) may be larger
than the decoded bytes.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Uint8List decode(String encoded) => decoder.convert(encoded);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/Base64Codec/decode.html>
:::
