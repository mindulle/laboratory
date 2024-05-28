[dart:html](../../dart-html/dart-html-library){._links-link}

getFile method
==============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[Entry](../entry-class)\>
getFile(

1.  [String](../../dart-core/string-class) path

)
:::

Retrieve an already existing file entry. The returned future will result
in an error if a file at `path` does not exist or if the item at `path`
is not a file.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<Entry> getFile(String path) {
  return _getFile(path);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/DirectoryEntry/getFile.html>
:::
