[dart:io](../../dart-io/dart-io-library){._links-link}

isDirectorySync method
======================

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) isDirectorySync(

1.  [String](../../dart-core/string-class) path

)
:::

Synchronously checks whether `path` refers to a directory.

Checks whether `typeSync(path)` returns
[FileSystemEntityType.directory](../filesystementitytype/directory-constant).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static bool isDirectorySync(String path) =>
    (_getTypeSync(_toUtf8Array(path), true) ==
        FileSystemEntityType.directory);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/FileSystemEntity/isDirectorySync.html>
:::
