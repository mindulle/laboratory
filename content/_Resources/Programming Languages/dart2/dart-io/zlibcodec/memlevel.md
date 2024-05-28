[dart:io](../../dart-io/dart-io-library){._links-link}

memLevel property
=================

::: {.section .multi-line-signature}
[int](../../dart-core/int-class) memLevel

::: {.features}
final
:::
:::

Specifies how much memory should be allocated for the internal
compression state. `1` uses minimum memory but is slow and reduces
compression ratio; `9` uses maximum memory for optimal speed. The
default value is `8`.

The memory requirements for deflate are (in bytes):

``` {.language-dart data-language="dart"}
(1 << (windowBits + 2)) +  (1 << (memLevel + 9))
```

that is: 128K for windowBits = 15 + 128K for memLevel = 8 (default
values)

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
final int memLevel;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/ZLibCodec/memLevel.html>
:::
