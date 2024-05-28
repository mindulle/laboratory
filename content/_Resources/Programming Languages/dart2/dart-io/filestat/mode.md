[dart:io](../../dart-io/dart-io-library){._links-link}

mode property
=============

::: {.section .multi-line-signature}
[int](../../dart-core/int-class) mode

::: {.features}
final
:::
:::

The mode of the file system object.

Permissions are encoded in the lower 16 bits of this number, and can be
decoded using the [modeString](modestring) getter.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
final int mode;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/FileStat/mode.html>
:::
