[dart:io](../../dart-io/dart-io-library){._links-link}

readByteSync method
===================

::: {.section .multi-line-signature}
[int](../../dart-core/int-class) readByteSync()
:::

Synchronously reads a byte from stdin.

This call will block until a byte is available.

If at end of file, -1 is returned.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external int readByteSync();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Stdin/readByteSync.html>
:::
