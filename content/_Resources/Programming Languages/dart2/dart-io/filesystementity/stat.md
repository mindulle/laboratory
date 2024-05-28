[dart:io](../../dart-io/dart-io-library){._links-link}

stat method
===========

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[FileStat](../filestat-class)\>
stat()
:::

Calls the operating system\'s `stat()` function on [path](path).

Identical to `FileStat.stat(this.path)`.

Returns a `Future<FileStat>` object containing the data returned by
`stat()`.

If [path](path) is a symbolic link then it is resolved and results for
the resulting file are returned.

If the call fails, completes the future with a `FileStat` object with
`.type` set to
[FileSystemEntityType.notFound](../filesystementitytype/notfound-constant)
and the other fields invalid.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<FileStat> stat() => FileStat.stat(path);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/FileSystemEntity/stat.html>
:::
