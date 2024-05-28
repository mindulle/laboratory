[dart:io](../../dart-io/dart-io-library){._links-link}

renameSync method
=================

::: {.section .multi-line-signature}
[FileSystemEntity](../filesystementity-class) renameSync(

1.  [String](../../dart-core/string-class) newPath

)
:::

Synchronously renames this file system entity.

Returns a [FileSystemEntity](../filesystementity-class) instance for the
renamed entity.

If `newPath` identifies an existing entity of the same type, that entity
is removed first. If `newPath` identifies an existing entity of a
different type, the operation fails and an exception is thrown.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
FileSystemEntity renameSync(String newPath);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/FileSystemEntity/renameSync.html>
:::
