[dart:io](../../dart-io/dart-io-library){._links-link}

create method
=============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[Link](../link-class)\> create(

1.  [String](../../dart-core/string-class) target,
2.  {[bool](../../dart-core/bool-class) recursive = false}

)
:::

Creates a symbolic link in the file system.

Returns a `Future<Link>` that completes with the link when it has been
created. If the link path already exists, the future will complete with
an error.

If `recursive` is `false`, the default, the link is created only if all
directories in its path exist. If `recursive` is `true`, all
non-existing parent paths are created first. The directories in the path
of `target` are not affected, unless they are also in
[path](../filesystementity/path).

On the Windows platform, this call will create a true symbolic link
instead of a Junction. In order to create a symbolic link on Windows,
Dart must be run in Administrator mode or the system must have Developer
Mode enabled, otherwise a
[FileSystemException](../filesystemexception-class) will be raised with
`ERROR_PRIVILEGE_NOT_HELD` set as the errno when this call is made.

On other platforms, the POSIX `symlink()` call is used to make a
symbolic link containing the string `target`. If `target` is a relative
path, it will be interpreted relative to the directory containing the
link.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<Link> create(String target, {bool recursive = false});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Link/create.html>
:::
