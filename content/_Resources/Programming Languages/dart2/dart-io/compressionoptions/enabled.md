[dart:io](../../dart-io/dart-io-library){._links-link}

enabled property
================

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) enabled

::: {.features}
final
:::
:::

Whether WebSocket compression is enabled.

If not enabled, the remaining fields have no effect, and the
[compressionOff](compressionoff-constant) instance can, and should, be
reused instead of creating a new instance with compression disabled.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
final bool enabled;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/CompressionOptions/enabled.html>
:::
