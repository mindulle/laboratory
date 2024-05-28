[dart:io](../../dart-io/dart-io-library){._links-link}

readByteSync method
===================

::: {.section .multi-line-signature}
[int](../../dart-core/int-class) readByteSync()
:::

Synchronously reads a single byte from the file.

If end-of-file has been reached -1 is returned.

Throws a [FileSystemException](../filesystemexception-class) if the
operation fails.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int readByteSync();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RandomAccessFile/readByteSync.html>
:::
