[dart:io](../../dart-io/dart-io-library){._links-link}

writeAsBytesSync method
=======================

::: {.section .multi-line-signature}
void writeAsBytesSync(

1.  [List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>
    bytes,
2.  {[FileMode](../filemode-class) mode = FileMode.write,
3.  [bool](../../dart-core/bool-class) flush = false}

)
:::

Synchronously writes a list of bytes to a file.

Opens the file, writes the list of bytes to it and closes the file.

By default [writeAsBytesSync](writeasbytessync) creates the file for
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
void writeAsBytesSync(List<int> bytes,
    {FileMode mode = FileMode.write, bool flush = false});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/File/writeAsBytesSync.html>
:::
