[dart:html](../../dart-html/dart-html-library){._links-link}

moveTo method
=============

::: {.section .multi-line-signature}
<div>

1.  \@JSName(\'moveTo\')

</div>

[Future](../../dart-async/future-class)\<[Entry](../entry-class)\>
moveTo(

1.  [DirectoryEntry](../directoryentry-class) parent,
2.  {[String](../../dart-core/string-class)? name}

)

::: {.features}
\@JSName(\'moveTo\')
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@JSName('moveTo')
Future<Entry> moveTo(DirectoryEntry parent, {String? name}) {
  var completer = new Completer<Entry>();
  _moveTo(parent, name, (value) {
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
<https://api.dart.dev/stable/2.18.5/dart-html/Entry/moveTo.html>
:::
