[dart:indexed\_db](../../dart-indexed_db/dart-indexed_db-library){._links-link}

completed property
==================

::: {#getter .section .multi-line-signature}
[Future](../../dart-async/future-class)\<[Database](../database-class)\>
completed
:::

Provides a Future which will be completed once the transaction has
completed.

The future will error if an error occurrs on the transaction or if the
transaction is aborted.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<Database> get completed {
  var completer = new Completer<Database>();

  this.onComplete.first.then((_) {
    completer.complete(db);
  });

  this.onError.first.then((e) {
    completer.completeError(e);
  });

  this.onAbort.first.then((e) {
    // Avoid completing twice if an error occurs.
    if (!completer.isCompleted) {
      completer.completeError(e);
    }
  });

  return completer.future;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-indexed_db/Transaction/completed.html>
:::
