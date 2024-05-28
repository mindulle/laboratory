[dart:io](../../dart-io/dart-io-library){._links-link}

fseGetType method
=================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[FileSystemEntityType](../filesystementitytype-class)\>
fseGetType(

1.  [String](../../dart-core/string-class) path,
2.  [bool](../../dart-core/bool-class) followLinks

)
:::

Asynchronously returns the `FileSystemEntityType` for `path`.

When this override is installed, this function overrides the behavior of
`FileSystemEntity.type`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<FileSystemEntityType> fseGetType(String path, bool followLinks) {
  return FileSystemEntity._getTypeRequest(
      utf8.encoder.convert(path), followLinks);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/IOOverrides/fseGetType.html>
:::
