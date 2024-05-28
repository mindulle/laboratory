[dart:io](../../dart-io/dart-io-library){._links-link}

writeString method
==================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[RandomAccessFile](../randomaccessfile-class)\>
writeString(

1.  [String](../../dart-core/string-class) string,
2.  {[Encoding](../../dart-convert/encoding-class) encoding = utf8}

)
:::

Writes a string to the file using the given
[Encoding](../../dart-convert/encoding-class).

Returns a `Future<RandomAccessFile>` that completes with this random
access file when the write completes.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<RandomAccessFile> writeString(String string,
    {Encoding encoding = utf8});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RandomAccessFile/writeString.html>
:::
