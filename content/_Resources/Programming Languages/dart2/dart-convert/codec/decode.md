[dart:convert](../../dart-convert/dart-convert-library){._links-link}

decode method
=============

::: {.section .multi-line-signature}
S decode(

1.  T encoded

)
:::

Decodes `encoded` data.

The input is decoded as if by `decoder.convert`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
S decode(T encoded) => decoder.convert(encoded);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/Codec/decode.html>
:::
