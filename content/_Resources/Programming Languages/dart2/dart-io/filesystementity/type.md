[dart:io](../../dart-io/dart-io-library){._links-link}

type method
===========

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[FileSystemEntityType](../filesystementitytype-class)\>
type(

1.  [String](../../dart-core/string-class) path,
2.  {[bool](../../dart-core/bool-class) followLinks = true}

)
:::

Finds the type of file system object that a path points to.

Returns a `Future<FileSystemEntityType>` that completes with the same
results as [typeSync](typesync).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static Future<FileSystemEntityType> type(String path,
    {bool followLinks = true}) {
  return _getType(_toUtf8Array(path), followLinks);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/FileSystemEntity/type.html>
:::
