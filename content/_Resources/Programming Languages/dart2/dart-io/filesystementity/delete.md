[dart:io](../../dart-io/dart-io-library){._links-link}

delete method
=============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[FileSystemEntity](../filesystementity-class)\>
delete(

1.  {[bool](../../dart-core/bool-class) recursive = false}

)
:::

Deletes this `FileSystemEntity`.

If the `FileSystemEntity` is a directory, and if `recursive` is `false`,
the directory must be empty. Otherwise, if `recursive` is true, the
directory and all sub-directories and files in the directories are
deleted. Links are not followed when deleting recursively. Only the link
is deleted, not its target.

If `recursive` is true, the `FileSystemEntity` is deleted even if the
type of the `FileSystemEntity` doesn\'t match the content of the file
system. This behavior allows [delete](delete) to be used to
unconditionally delete any file system object.

Returns a `Future<FileSystemEntity>` that completes with this
`FileSystemEntity` when the deletion is done. If the `FileSystemEntity`
cannot be deleted, the future completes with an exception.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<FileSystemEntity> delete({bool recursive = false}) =>
    _delete(recursive: recursive);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/FileSystemEntity/delete.html>
:::
