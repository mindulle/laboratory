[dart:io](../../dart-io/dart-io-library){._links-link}

rename method
=============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[Directory](../directory-class)\>
rename(

1.  [String](../../dart-core/string-class) newPath

)

::: {.features}
override
:::
:::

Renames this directory.

Returns a `Future<Directory>` that completes with a `Directory` for the
renamed directory.

If `newPath` identifies an existing directory, then the behavior is
platform-specific. On all platforms, the future completes with a
[FileSystemException](../filesystemexception-class) if the existing
directory is not empty. On POSIX systems, if `newPath` identifies an
existing empty directory then that directory is deleted before this
directory is renamed.

If `newPath` identifies an existing file, the operation fails and the
future completes with a
[FileSystemException](../filesystemexception-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<Directory> rename(String newPath);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Directory/rename.html>
:::
