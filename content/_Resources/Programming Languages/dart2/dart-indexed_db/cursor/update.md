[dart:indexed\_db](../../dart-indexed_db/dart-indexed_db-library){._links-link}

update method
=============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) update(

1.  dynamic value

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future update(value) {
  try {
    return _completeRequest(_update(value));
  } catch (e, stacktrace) {
    return new Future.error(e, stacktrace);
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-indexed_db/Cursor/update.html>
:::
