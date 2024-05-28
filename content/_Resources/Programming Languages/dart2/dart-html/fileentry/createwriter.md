[dart:html](../../dart-html/dart-html-library){._links-link}

createWriter method
===================

::: {.section .multi-line-signature}
<div>

1.  \@JSName(\'createWriter\')

</div>

[Future](../../dart-async/future-class)\<[FileWriter](../filewriter-class)\>
createWriter()

::: {.features}
\@JSName(\'createWriter\')
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@JSName('createWriter')
Future<FileWriter> createWriter() {
  var completer = new Completer<FileWriter>();
  _createWriter((value) {
    applyExtension('FileWriter', value);
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
<https://api.dart.dev/stable/2.18.5/dart-html/FileEntry/createWriter.html>
:::
