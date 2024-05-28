[dart:io](../../dart-io/dart-io-library){._links-link}

setPosition method
==================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[RandomAccessFile](../randomaccessfile-class)\>
setPosition(

1.  [int](../../dart-core/int-class) position

)
:::

Sets the byte position in the file.

Returns a `Future<RandomAccessFile>` that completes with this random
access file when the position has been set.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<RandomAccessFile> setPosition(int position);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RandomAccessFile/setPosition.html>
:::
