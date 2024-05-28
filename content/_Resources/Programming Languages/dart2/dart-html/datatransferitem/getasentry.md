[dart:html](../../dart-html/dart-html-library){._links-link}

getAsEntry method
=================

::: {.section .multi-line-signature}
[Entry](../entry-class) getAsEntry()
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Entry getAsEntry() {
  Entry entry = _webkitGetAsEntry() as Entry;

  if (entry.isFile!) {
    applyExtension('FileEntry', entry);
    applyExtension('webkitFileSystemFileEntry', entry);
    applyExtension('FileSystemFileEntry', entry);
  } else if (entry.isDirectory!) {
    applyExtension('DirectoryEntry', entry);
    applyExtension('webkitFileSystemDirectoryEntry', entry);
    applyExtension('FileSystemDirectoryEntry', entry);
  } else {
    applyExtension('Entry', entry);
    applyExtension('webkitFileSystemEntry', entry);
    applyExtension('FileSystemEntry', entry);
  }

  return entry;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/DataTransferItem/getAsEntry.html>
:::
