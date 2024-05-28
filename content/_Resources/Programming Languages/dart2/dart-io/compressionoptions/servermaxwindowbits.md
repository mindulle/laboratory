[dart:io](../../dart-io/dart-io-library){._links-link}

serverMaxWindowBits property
============================

::: {.section .multi-line-signature}
[int](../../dart-core/int-class)? serverMaxWindowBits

::: {.features}
final
:::
:::

The maximal window size bit count requested by the server.

The windows size for the compression is always a power of two, so the
number of bits precisely determines the window size.

If set to `null`, the server has no preference, and the compression can
use up to its default maximum window size of 15 bits depending on the
client\'s preference.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
final int? serverMaxWindowBits;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/CompressionOptions/serverMaxWindowBits.html>
:::
