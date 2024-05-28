[dart:io](../../dart-io/dart-io-library){._links-link}

existsSync method
=================

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) existsSync()
:::

Synchronously checks whether the file system entity with this path
exists.

Since [FileSystemEntity](../filesystementity-class) is abstract, every
[FileSystemEntity](../filesystementity-class) object is actually an
instance of one of the subclasses [File](../file-class),
[Directory](../directory-class), and [Link](../link-class). Calling
[existsSync](existssync) on an instance of one of these subclasses
checks whether the object exists in the file system object exists and is
of the correct type (file, directory, or link). To check whether a path
points to an object on the file system, regardless of the object\'s
type, use the [typeSync](typesync) static method.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool existsSync();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/FileSystemEntity/existsSync.html>
:::
