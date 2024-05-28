[dart:html](../../dart-html/dart-html-library){._links-link}

getParent method
================

::: {.section .multi-line-signature}
<div>

1.  \@JSName(\'getParent\')

</div>

[Future](../../dart-async/future-class)\<[Entry](../entry-class)\>
getParent()

::: {.features}
\@JSName(\'getParent\')
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@JSName('getParent')
Future<Entry> getParent() {
  var completer = new Completer<Entry>();
  _getParent((value) {
    applyExtension('Entry', value);
    applyExtension('webkitFileSystemEntry', value);
    applyExtension('FileSystemEntry', value);
    completer.complete(value);
  }, (error) {
    completer.completeError(error);
  });
  return completer.future;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Entry/getParent.html>
:::
