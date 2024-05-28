[dart:io](../../dart-io/dart-io-library){._links-link}

writeStringSync method
======================

::: {.section .multi-line-signature}
void writeStringSync(

1.  [String](../../dart-core/string-class) string,
2.  {[Encoding](../../dart-convert/encoding-class) encoding = utf8}

)
:::

Synchronously writes a single string to the file using the given
[Encoding](../../dart-convert/encoding-class).

Throws a [FileSystemException](../filesystemexception-class) if the
operation fails.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void writeStringSync(String string, {Encoding encoding = utf8});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RandomAccessFile/writeStringSync.html>
:::
