[dart:io](../../dart-io/dart-io-library){._links-link}

windowBits property
===================

::: {.section .multi-line-signature}
[int](../../dart-core/int-class) windowBits

::: {.features}
final
:::
:::

Base two logarithm of the window size (the size of the history buffer).
It should be in the range 8..15. Larger values result in better
compression at the expense of memory usage. The default value is 15

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
final int windowBits;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/ZLibCodec/windowBits.html>
:::
