[dart:io](../../dart-io/dart-io-library){._links-link}

identicalSync method
====================

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) identicalSync(

1.  [String](../../dart-core/string-class) path1,
2.  [String](../../dart-core/string-class) path2

)
:::

Synchronously checks whether two paths refer to the same object in the
file system.

Comparing a link to its target returns `false`, as does comparing two
links that point to the same target. To check the target of a link, use
Link.target explicitly to fetch it. Directory links appearing inside a
path are followed, though, to find the file system object.

Throws an error if one of the paths points to an object that does not
exist.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static bool identicalSync(String path1, String path2) {
  IOOverrides? overrides = IOOverrides.current;
  if (overrides == null) {
    return _identicalSync(path1, path2);
  }
  return overrides.fseIdenticalSync(path1, path2);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/FileSystemEntity/identicalSync.html>
:::
