[dart:io](../../dart-io/dart-io-library){._links-link}

truncateSync method
===================

::: {.section .multi-line-signature}
void truncateSync(

1.  [int](../../dart-core/int-class) length

)
:::

Synchronously truncates (or extends) the file to `length` bytes.

Throws a [FileSystemException](../filesystemexception-class) if the
operation fails.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void truncateSync(int length);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RandomAccessFile/truncateSync.html>
:::
