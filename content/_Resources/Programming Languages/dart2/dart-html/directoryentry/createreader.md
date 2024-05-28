[dart:html](../../dart-html/dart-html-library){._links-link}

createReader method
===================

::: {.section .multi-line-signature}
[DirectoryReader](../directoryreader-class) createReader()
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
DirectoryReader createReader() {
  DirectoryReader reader = _createReader();
  applyExtension('DirectoryReader', reader);
  applyExtension('WebKitDirectoryReader', reader);
  applyExtension('webkitFileSystemDirectoryReader', reader);
  applyExtension('FileSystemDirectoryReader', reader);
  return reader;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/DirectoryEntry/createReader.html>
:::
