[dart:html](../../dart-html/dart-html-library){._links-link}

remove method
=============

::: {.section .multi-line-signature}
<div>

1.  \@JSName(\'remove\')

</div>

[Future](../../dart-async/future-class) remove()

::: {.features}
\@JSName(\'remove\')
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@JSName('remove')
Future remove() {
  var completer = new Completer();
  _remove(() {
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
<https://api.dart.dev/stable/2.18.5/dart-html/Entry/remove.html>
:::
