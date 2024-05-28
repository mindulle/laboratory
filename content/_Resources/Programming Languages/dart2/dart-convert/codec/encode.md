[dart:convert](../../dart-convert/dart-convert-library){._links-link}

encode method
=============

::: {.section .multi-line-signature}
T encode(

1.  S input

)
:::

Encodes `input`.

The input is encoded as if by `encoder.convert`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
T encode(S input) => encoder.convert(input);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/Codec/encode.html>
:::
