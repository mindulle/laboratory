[dart:io](../../dart-io/dart-io-library){._links-link}

deleteSync method
=================

::: {.section .multi-line-signature}
void deleteSync(

1.  {[bool](../../dart-core/bool-class) recursive = false}

)
:::

Synchronously deletes this
[FileSystemEntity](../filesystementity-class).

If the [FileSystemEntity](../filesystementity-class) is a directory, and
if `recursive` is false, the directory must be empty. Otherwise, if
`recursive` is true, the directory and all sub-directories and files in
the directories are deleted. Links are not followed when deleting
recursively. Only the link is deleted, not its target.

If `recursive` is true, the
[FileSystemEntity](../filesystementity-class) is deleted even if the
type of the [FileSystemEntity](../filesystementity-class) doesn\'t match
the content of the file system. This behavior allows
[deleteSync](deletesync) to be used to unconditionally delete any file
system object.

Throws an exception if the [FileSystemEntity](../filesystementity-class)
cannot be deleted.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void deleteSync({bool recursive = false}) =>
    _deleteSync(recursive: recursive);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/FileSystemEntity/deleteSync.html>
:::
