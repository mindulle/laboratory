[dart:io](../../dart-io/dart-io-library){._links-link}

readSync method
===============

::: {.section .multi-line-signature}
[Uint8List](../../dart-typed_data/uint8list-class) readSync(

1.  [int](../../dart-core/int-class) count

)
:::

Synchronously reads up to `count` bytes from a file

Throws a [FileSystemException](../filesystemexception-class) if the
operation fails.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Uint8List readSync(int count);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RandomAccessFile/readSync.html>
:::
