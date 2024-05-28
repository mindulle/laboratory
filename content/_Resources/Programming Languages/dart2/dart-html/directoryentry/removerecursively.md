[dart:html](../../dart-html/dart-html-library){._links-link}

removeRecursively method
========================

::: {.section .multi-line-signature}
<div>

1.  \@JSName(\'removeRecursively\')

</div>

[Future](../../dart-async/future-class) removeRecursively()

::: {.features}
\@JSName(\'removeRecursively\')
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@JSName('removeRecursively')
Future removeRecursively() {
  var completer = new Completer();
  _removeRecursively(() {
    completer.complete();
  }, (error) {
    completer.completeError(error);
  });
  return completer.future;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/DirectoryEntry/removeRecursively.html>
:::
