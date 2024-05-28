[dart:io](../../dart-io/dart-io-library){._links-link}

writeByte method
================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[RandomAccessFile](../randomaccessfile-class)\>
writeByte(

1.  [int](../../dart-core/int-class) value

)
:::

Writes a single byte to the file.

Returns a `Future<RandomAccessFile>` that completes with this random
access file when the write completes.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<RandomAccessFile> writeByte(int value);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RandomAccessFile/writeByte.html>
:::
