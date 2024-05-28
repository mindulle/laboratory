[dart:io](../../dart-io/dart-io-library){._links-link}

list method
===========

::: {.section .multi-line-signature}
[Stream](../../dart-async/stream-class)\<[FileSystemEntity](../filesystementity-class)\>
list(

1.  {[bool](../../dart-core/bool-class) recursive = false,
2.  [bool](../../dart-core/bool-class) followLinks = true}

)
:::

Lists the sub-directories and files of this
[Directory](../directory-class).

Optionally recurses into sub-directories.

If `followLinks` is `false`, then any symbolic links found are reported
as [Link](../link-class) objects, rather than as directories or files,
and are not recursed into.

If `followLinks` is `true`, then working links are reported as
directories or files, depending on what they point to, and links to
directories are recursed into f `recursive` is `true`.

Broken links are reported as [Link](../link-class) objects.

If a symbolic link makes a loop in the file system, then a recursive
listing will not follow a link twice in the same recursive descent, but
will report it as a [Link](../link-class) the second time it is seen.

The result is a stream of `FileSystemEntity` objects for the
directories, files, and links.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<FileSystemEntity> list(
    {bool recursive = false, bool followLinks = true});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Directory/list.html>
:::
