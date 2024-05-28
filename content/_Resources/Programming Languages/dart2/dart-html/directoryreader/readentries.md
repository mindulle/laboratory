[dart:html](../../dart-html/dart-html-library){._links-link}

readEntries method
==================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[List](../../dart-core/list-class)\<[Entry](../entry-class)\>\>
readEntries()
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<List<Entry>> readEntries() {
  var completer = new Completer<List<Entry>>();
  _readEntries((values) {
    values.forEach((value) {
      applyExtension('Entry', value);
      applyExtension('webkitFileSystemEntry', value);
      applyExtension('FileSystemEntry', value);
      Entry entry = value as Entry;
      if (entry.isFile!) {
        applyExtension('FileEntry', entry);
        applyExtension('webkitFileSystemFileEntry', entry);
        applyExtension('FileSystemFileEntry', entry);
      } else if (entry.isDirectory!) {
        applyExtension('DirectoryEntry', entry);
        applyExtension('webkitFileSystemDirectoryEntry', entry);
        applyExtension('FileSystemDirectoryEntry', entry);
      }
    });
    completer.complete(new List<Entry>.from(values));
  }, (error) {
    completer.completeError(error);
  });

  return completer.future;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/DirectoryReader/readEntries.html>
:::
