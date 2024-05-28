[dart:io](../../dart-io/dart-io-library){._links-link}

writeAsString method
====================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[File](../file-class)\>
writeAsString(

1.  [String](../../dart-core/string-class) contents,
2.  {[FileMode](../filemode-class) mode = FileMode.write,
3.  [Encoding](../../dart-convert/encoding-class) encoding = utf8,
4.  [bool](../../dart-core/bool-class) flush = false}

)
:::

Writes a string to a file.

Opens the file, writes the string in the given encoding, and closes the
file. Returns a `Future<File>` that completes with this `File` object
once the entire operation has completed.

By default [writeAsString](writeasstring) creates the file for writing
and truncates the file if it already exists. In order to append the
bytes to an existing file, pass
[FileMode.append](../filemode/append-constant) as the optional mode
parameter.

If the argument `flush` is set to `true`, the data written will be
flushed to the file system before the returned future completes.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<File> writeAsString(String contents,
    {FileMode mode = FileMode.write,
    Encoding encoding = utf8,
    bool flush = false});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/File/writeAsString.html>
:::
