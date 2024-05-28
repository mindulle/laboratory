[dart:io](../../dart-io/dart-io-library){._links-link}

rename method
=============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[FileSystemEntity](../filesystementity-class)\>
rename(

1.  [String](../../dart-core/string-class) newPath

)
:::

Renames this file system entity.

Returns a `Future<FileSystemEntity>` that completes with a
`FileSystemEntity` instance for the renamed file system entity.

If `newPath` identifies an existing entity of the same type, that entity
is removed first. If `newPath` identifies an existing entity of a
different type, the operation fails and the future completes with an
exception.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<FileSystemEntity> rename(String newPath);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/FileSystemEntity/rename.html>
:::
