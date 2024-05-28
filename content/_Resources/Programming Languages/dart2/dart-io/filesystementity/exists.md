[dart:io](../../dart-io/dart-io-library){._links-link}

exists method
=============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[bool](../../dart-core/bool-class)\>
exists()
:::

Checks whether the file system entity with this path exists.

Returns a `Future<bool>` that completes with the result.

Since [FileSystemEntity](../filesystementity-class) is abstract, every
[FileSystemEntity](../filesystementity-class) object is actually an
instance of one of the subclasses [File](../file-class),
[Directory](../directory-class), and [Link](../link-class). Calling
[exists](exists) on an instance of one of these subclasses checks
whether the object exists in the file system object exists *and* is of
the correct type (file, directory, or link). To check whether a path
points to an object on the file system, regardless of the object\'s
type, use the [type](type) static method.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<bool> exists();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/FileSystemEntity/exists.html>
:::
