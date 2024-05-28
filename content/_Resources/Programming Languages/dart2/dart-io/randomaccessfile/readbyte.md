[dart:io](../../dart-io/dart-io-library){._links-link}

readByte method
===============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[int](../../dart-core/int-class)\>
readByte()
:::

Reads a byte from the file.

Returns a `Future<int>` that completes with the byte, or with -1 if
end-of-file has been reached.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<int> readByte();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RandomAccessFile/readByte.html>
:::
