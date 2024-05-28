[dart:io](../../dart-io/dart-io-library){._links-link}

strategy property
=================

::: {.section .multi-line-signature}
[int](../../dart-core/int-class) strategy

::: {.features}
final
:::
:::

Tunes the compression algorithm. Use the value
[ZLibOption.strategyDefault](../zliboption/strategydefault-constant) for
normal data,
[ZLibOption.strategyFiltered](../zliboption/strategyfiltered-constant)
for data produced by a filter (or predictor),
[ZLibOption.strategyHuffmanOnly](../zliboption/strategyhuffmanonly-constant)
to force Huffman encoding only (no string match), or
[ZLibOption.strategyRle](../zliboption/strategyrle-constant) to limit
match distances to one (run-length encoding).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
final int strategy;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/ZLibEncoder/strategy.html>
:::
