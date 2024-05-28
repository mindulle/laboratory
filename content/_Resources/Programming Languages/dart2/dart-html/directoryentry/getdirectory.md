[dart:html](../../dart-html/dart-html-library){._links-link}

getDirectory method
===================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[Entry](../entry-class)\>
getDirectory(

1.  [String](../../dart-core/string-class) path

)
:::

Retrieve an already existing directory entry. The returned future will
result in an error if a directory at `path` does not exist or if the
item at `path` is not a directory.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<Entry> getDirectory(String path) {
  return _getDirectory(path);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/DirectoryEntry/getDirectory.html>
:::
