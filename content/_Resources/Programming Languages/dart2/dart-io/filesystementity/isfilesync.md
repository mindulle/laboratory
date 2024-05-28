[dart:io](../../dart-io/dart-io-library){._links-link}

isFileSync method
=================

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) isFileSync(

1.  [String](../../dart-core/string-class) path

)
:::

Synchronously checks whether `path` refers to a file.

Checks whether `typeSync(path)` returns
[FileSystemEntityType.file](../filesystementitytype/file-constant).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static bool isFileSync(String path) =>
    (_getTypeSync(_toUtf8Array(path), true) == FileSystemEntityType.file);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/FileSystemEntity/isFileSync.html>
:::
