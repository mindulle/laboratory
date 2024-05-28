[dart:io](../../dart-io/dart-io-library){._links-link}

FileSystemException constructor
===============================

::: {.section .multi-line-signature}
const FileSystemException(

1.  \[[String](../../dart-core/string-class) message = \"\",
2.  [String](../../dart-core/string-class)? path = \"\",
3.  [OSError](../oserror-class)? osError\]

)
:::

Creates a new file system exception with optional parts.

Creates an exception with [FileSystemException.message](message),
[FileSystemException.path](path) and
[FileSystemException.osError](oserror) values take from the optional
parameters of the same name.

The [message](message) and [path](path) path defaults to empty strings
if omitted, and [osError](oserror) defaults to `null`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@pragma("vm:entry-point")
const FileSystemException([this.message = "", this.path = "", this.osError]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/FileSystemException/FileSystemException.html>
:::
