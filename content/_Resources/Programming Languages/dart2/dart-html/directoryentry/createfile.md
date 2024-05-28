[dart:html](../../dart-html/dart-html-library){._links-link}

createFile method
=================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[Entry](../entry-class)\>
createFile(

1.  [String](../../dart-core/string-class) path,
2.  {[bool](../../dart-core/bool-class) exclusive = false}

)
:::

Create a new file with the specified `path`. If `exclusive` is true, the
returned Future will complete with an error if a file already exists at
the specified `path`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<Entry> createFile(String path, {bool exclusive: false}) {
  return _getFile(path, options: {'create': true, 'exclusive': exclusive});
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/DirectoryEntry/createFile.html>
:::
