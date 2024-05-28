[dart:io](../../dart-io/dart-io-library){._links-link}

Directory constructor
=====================

::: {.section .multi-line-signature}
Directory(

1.  [String](../../dart-core/string-class) path

)
:::

Creates a [Directory](../directory-class) object.

If `path` is a relative path, it will be interpreted relative to the
current working directory (see [Directory.current](current)), when used.

If `path` is an absolute path, it will be immune to changes to the
current working directory.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@pragma("vm:entry-point")
factory Directory(String path) {
  final IOOverrides? overrides = IOOverrides.current;
  if (overrides == null) {
    return new _Directory(path);
  }
  return overrides.createDirectory(path);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Directory/Directory.html>
:::
