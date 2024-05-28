[dart:io](../../dart-io/dart-io-library){._links-link}

renameSync method
=================

::: {.section .multi-line-signature}
[Directory](../directory-class) renameSync(

1.  [String](../../dart-core/string-class) newPath

)

::: {.features}
override
:::
:::

Synchronously renames this directory.

Returns a [Directory](../directory-class) for the renamed directory.

If `newPath` identifies an existing directory, then the behavior is
platform-specific. On all platforms, a
[FileSystemException](../filesystemexception-class) is thrown if the
existing directory is not empty. On POSIX systems, if `newPath`
identifies an existing empty directory then that directory is deleted
before this directory is renamed.

If `newPath` identifies an existing file the operation fails and a
[FileSystemException](../filesystemexception-class) is thrown.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Directory renameSync(String newPath);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Directory/renameSync.html>
:::
