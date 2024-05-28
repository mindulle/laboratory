[dart:io](../../dart-io/dart-io-library){._links-link}

fseGetTypeSync method
=====================

::: {.section .multi-line-signature}
[FileSystemEntityType](../filesystementitytype-class) fseGetTypeSync(

1.  [String](../../dart-core/string-class) path,
2.  [bool](../../dart-core/bool-class) followLinks

)
:::

Returns the [FileSystemEntityType](../filesystementitytype-class) for
`path`.

When this override is installed, this function overrides the behavior of
`FileSystemEntity.typeSync`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
FileSystemEntityType fseGetTypeSync(String path, bool followLinks) {
  return FileSystemEntity._getTypeSyncHelper(
      utf8.encoder.convert(path), followLinks);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/IOOverrides/fseGetTypeSync.html>
:::
