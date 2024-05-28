[dart:io](../../dart-io/dart-io-library){._links-link}

writeByteSync method
====================

::: {.section .multi-line-signature}
[int](../../dart-core/int-class) writeByteSync(

1.  [int](../../dart-core/int-class) value

)
:::

Synchronously writes a single byte to the file.

Returns 1 on success.

Throws a [FileSystemException](../filesystemexception-class) if the
operation fails.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int writeByteSync(int value);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RandomAccessFile/writeByteSync.html>
:::
