[dart:io](../../dart-io/dart-io-library){._links-link}

fseIdenticalSync method
=======================

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) fseIdenticalSync(

1.  [String](../../dart-core/string-class) path1,
2.  [String](../../dart-core/string-class) path2

)
:::

Returns `true` if `path1` and `path2` are paths to the same file system
object.

When this override is installed, this function overrides the behavior of
`FileSystemEntity.identicalSync`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool fseIdenticalSync(String path1, String path2) {
  return FileSystemEntity._identicalSync(path1, path2);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/IOOverrides/fseIdenticalSync.html>
:::
