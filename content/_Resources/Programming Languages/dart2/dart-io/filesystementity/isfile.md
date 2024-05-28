[dart:io](../../dart-io/dart-io-library){._links-link}

isFile method
=============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[bool](../../dart-core/bool-class)\>
isFile(

1.  [String](../../dart-core/string-class) path

)
:::

Whether `path` refers to a file.

Checks whether `type(path)` returns
[FileSystemEntityType.file](../filesystementitytype/file-constant).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static Future<bool> isFile(String path) => _getType(_toUtf8Array(path), true)
    .then((type) => (type == FileSystemEntityType.file));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/FileSystemEntity/isFile.html>
:::
