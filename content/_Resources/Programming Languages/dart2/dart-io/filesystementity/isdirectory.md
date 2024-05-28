[dart:io](../../dart-io/dart-io-library){._links-link}

isDirectory method
==================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[bool](../../dart-core/bool-class)\>
isDirectory(

1.  [String](../../dart-core/string-class) path

)
:::

Whether `path` refers to a directory.

Checks whether `type(path)` returns
[FileSystemEntityType.directory](../filesystementitytype/directory-constant).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static Future<bool> isDirectory(String path) =>
    _getType(_toUtf8Array(path), true)
        .then((type) => (type == FileSystemEntityType.directory));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/FileSystemEntity/isDirectory.html>
:::
