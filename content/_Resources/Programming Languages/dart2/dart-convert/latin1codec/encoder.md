[dart:convert](../../dart-convert/dart-convert-library){._links-link}

encoder property
================

::: {#getter .section .multi-line-signature}
[Latin1Encoder](../latin1encoder-class) encoder

::: {.features}
override
:::
:::

Returns the encoder from `String` to `List<int>`.

It may be stateful and should not be reused.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Latin1Encoder get encoder => const Latin1Encoder();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/Latin1Codec/encoder.html>
:::
