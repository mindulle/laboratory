[dart:io](../../dart-io/dart-io-library){._links-link}

fseIdentical method
===================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[bool](../../dart-core/bool-class)\>
fseIdentical(

1.  [String](../../dart-core/string-class) path1,
2.  [String](../../dart-core/string-class) path2

)
:::

Asynchronously returns `true` if `path1` and `path2` are paths to the
same file system object.

When this override is installed, this function overrides the behavior of
`FileSystemEntity.identical`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<bool> fseIdentical(String path1, String path2) {
  return FileSystemEntity._identical(path1, path2);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/IOOverrides/fseIdentical.html>
:::
