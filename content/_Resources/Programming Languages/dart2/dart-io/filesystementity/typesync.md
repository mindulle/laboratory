[dart:io](../../dart-io/dart-io-library){._links-link}

typeSync method
===============

::: {.section .multi-line-signature}
[FileSystemEntityType](../filesystementitytype-class) typeSync(

1.  [String](../../dart-core/string-class) path,
2.  {[bool](../../dart-core/bool-class) followLinks = true}

)
:::

Synchronously finds the type of file system object that a path points
to.

Returns
[FileSystemEntityType.link](../filesystementitytype/link-constant) only
if `followLinks` is `false` and if `path` points to a link.

Returns
[FileSystemEntityType.notFound](../filesystementitytype/notfound-constant)
if `path` does not point to a file system object or if any other error
occurs in looking up the path.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static FileSystemEntityType typeSync(String path, {bool followLinks = true}) {
  return _getTypeSync(_toUtf8Array(path), followLinks);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/FileSystemEntity/typeSync.html>
:::
