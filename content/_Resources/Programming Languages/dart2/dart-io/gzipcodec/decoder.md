[dart:io](../../dart-io/dart-io-library){._links-link}

decoder property
================

::: {#getter .section .multi-line-signature}
[ZLibDecoder](../zlibdecoder-class) decoder

::: {.features}
override
:::
:::

Get a [ZLibDecoder](../zlibdecoder-class) for decoding `GZip` compressed
data.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
ZLibDecoder get decoder =>
    new ZLibDecoder(windowBits: windowBits, dictionary: dictionary, raw: raw);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/GZipCodec/decoder.html>
:::
