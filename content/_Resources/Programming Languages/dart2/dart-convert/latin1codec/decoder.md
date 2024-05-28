[dart:convert](../../dart-convert/dart-convert-library){._links-link}

decoder property
================

::: {#getter .section .multi-line-signature}
[Latin1Decoder](../latin1decoder-class) decoder

::: {.features}
override
:::
:::

Returns the decoder of `this`, converting from `List<int>` to `String`.

It may be stateful and should not be reused.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Latin1Decoder get decoder => _allowInvalid
    ? const Latin1Decoder(allowInvalid: true)
    : const Latin1Decoder(allowInvalid: false);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/Latin1Codec/decoder.html>
:::
