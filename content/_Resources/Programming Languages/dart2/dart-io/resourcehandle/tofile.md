[dart:io](../../dart-io/dart-io-library){._links-link}

toFile method
=============

::: {.section .multi-line-signature}
[RandomAccessFile](../randomaccessfile-class) toFile()
:::

Extracts opened file from resource handle.

This can also be used when receiving stdin and stdout handles.

If this resource handle is not a file or stdio handle, the behavior of
the returned [RandomAccessFile](../randomaccessfile-class) is completely
unspecified. Be very careful to avoid using a handle incorrectly.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
RandomAccessFile toFile();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/ResourceHandle/toFile.html>
:::
