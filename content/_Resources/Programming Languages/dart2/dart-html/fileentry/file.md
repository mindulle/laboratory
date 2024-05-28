[dart:html](../../dart-html/dart-html-library){._links-link}

file method
===========

::: {.section .multi-line-signature}
<div>

1.  \@JSName(\'file\')

</div>

[Future](../../dart-async/future-class)\<[File](../file-class)\> file()

::: {.features}
\@JSName(\'file\')
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@JSName('file')
Future<File> file() {
  var completer = new Completer<File>();
  _file((value) {
    applyExtension('File', value);
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
<https://api.dart.dev/stable/2.18.5/dart-html/FileEntry/file.html>
:::
