[dart:io](../../dart-io/dart-io-library){._links-link}

absolute property
=================

::: {#getter .section .multi-line-signature}
[FileSystemEntity](../filesystementity-class) absolute
:::

A [FileSystemEntity](../filesystementity-class) whose path is the
absolute path of [path](path).

The type of the returned instance is the same as the type of this
entity.

A file system entity with an already absolute path (as reported by
[isAbsolute](isabsolute)) is returned directly. For a non-absolute path,
the returned entity is absolute ([isAbsolute](isabsolute)) *if
possible*, but still refers to the same file system object.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
FileSystemEntity get absolute;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/FileSystemEntity/absolute.html>
:::
