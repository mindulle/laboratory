[dart:io](../../dart-io/dart-io-library){._links-link}

File.fromRawPath constructor
============================

::: {.section .multi-line-signature}
File.fromRawPath(

1.  [Uint8List](../../dart-typed_data/uint8list-class) rawPath

)
:::

Creates a [File](../file-class) object from a raw path.

A raw path is a sequence of bytes, as paths are represented by the OS.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@pragma("vm:entry-point")
factory File.fromRawPath(Uint8List rawPath) {
  // TODO(bkonyi): Handle overrides.
  return new _File.fromRawPath(rawPath);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/File/File.fromRawPath.html>
:::
