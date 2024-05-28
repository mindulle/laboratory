[dart:io](../../dart-io/dart-io-library){._links-link}

writeAsStringSync method
========================

::: {.section .multi-line-signature}
void writeAsStringSync(

1.  [String](../../dart-core/string-class) contents,
2.  {[FileMode](../filemode-class) mode = FileMode.write,
3.  [Encoding](../../dart-convert/encoding-class) encoding = utf8,
4.  [bool](../../dart-core/bool-class) flush = false}

)
:::

Synchronously writes a string to a file.

Opens the file, writes the string in the given encoding, and closes the
file.

By default [writeAsStringSync](writeasstringsync) creates the file for
writing and truncates the file if it already exists. In order to append
the bytes to an existing file, pass
[FileMode.append](../filemode/append-constant) as the optional mode
parameter.

If the `flush` argument is set to `true` data written will be flushed to
the file system before returning.

Throws a [FileSystemException](../filesystemexception-class) if the
operation fails.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void writeAsStringSync(String contents,
    {FileMode mode = FileMode.write,
    Encoding encoding = utf8,
    bool flush = false});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/File/writeAsStringSync.html>
:::
