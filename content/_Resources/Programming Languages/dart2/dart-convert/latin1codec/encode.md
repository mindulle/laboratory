[dart:convert](../../dart-convert/dart-convert-library){._links-link}

encode method
=============

::: {.section .multi-line-signature}
[Uint8List](../../dart-typed_data/uint8list-class) encode(

1.  [String](../../dart-core/string-class) source

)

::: {.features}
override
:::
:::

Encodes `input`.

The input is encoded as if by `encoder.convert`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Uint8List encode(String source) => encoder.convert(source);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/Latin1Codec/encode.html>
:::
