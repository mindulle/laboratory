[dart:io](../../dart-io/dart-io-library){._links-link}

truncate method
===============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[RandomAccessFile](../randomaccessfile-class)\>
truncate(

1.  [int](../../dart-core/int-class) length

)
:::

Truncates (or extends) the file to `length` bytes.

Returns a `Future<RandomAccessFile>` that completes with this random
access file when the truncation has been performed.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<RandomAccessFile> truncate(int length);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RandomAccessFile/truncate.html>
:::
