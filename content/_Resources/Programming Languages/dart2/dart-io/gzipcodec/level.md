[dart:io](../../dart-io/dart-io-library){._links-link}

level property
==============

::: {.section .multi-line-signature}
[int](../../dart-core/int-class) level

::: {.features}
final
:::
:::

The compression-[level](level) can be set in the range of `-1..9`, with
`6` being the default compression level. Levels above `6` will have
higher compression rates at the cost of more CPU and memory usage.
Levels below `6` will use less CPU and memory at the cost of lower
compression rates.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
final int level;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/GZipCodec/level.html>
:::
