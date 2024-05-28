[dart:io](../../dart-io/dart-io-library){._links-link}

encoder property
================

::: {#getter .section .multi-line-signature}
[ZLibEncoder](../zlibencoder-class) encoder

::: {.features}
override
:::
:::

Get a [ZLibEncoder](../zlibencoder-class) for encoding to `ZLib`
compressed data.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
ZLibEncoder get encoder => new ZLibEncoder(
    gzip: false,
    level: level,
    windowBits: windowBits,
    memLevel: memLevel,
    strategy: strategy,
    dictionary: dictionary,
    raw: raw);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/ZLibCodec/encoder.html>
:::
