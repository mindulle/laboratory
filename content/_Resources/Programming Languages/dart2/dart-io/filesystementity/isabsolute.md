[dart:io](../../dart-io/dart-io-library){._links-link}

isAbsolute property
===================

::: {#getter .section .multi-line-signature}
[bool](../../dart-core/bool-class) isAbsolute
:::

Whether this object\'s path is absolute.

An absolute path is independent of the current working directory
([Directory.current](../directory/current)). A non-absolute path must be
interpreted relative to the current working directory.

On Windows, a path is absolute if it starts with `\\` (two backslashes
or representing a UNC path) or with a drive letter between `a` and `z`
(upper or lower case) followed by `:\` or `:/`. This makes, for example,
`\file.ext` a non-absolute path because it depends on the current drive
letter.

On non-Windows, a path is absolute if it starts with `/`.

If the path is not absolute, use [absolute](absolute) to get an entity
with an absolute path referencing the same object in the file system, if
possible.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool get isAbsolute => _isAbsolute(path);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/FileSystemEntity/isAbsolute.html>
:::
