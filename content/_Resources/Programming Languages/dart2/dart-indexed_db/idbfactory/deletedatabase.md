[dart:indexed\_db](../../dart-indexed_db/dart-indexed_db-library){._links-link}

deleteDatabase method
=====================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[IdbFactory](../idbfactory-class)\>
deleteDatabase(

1.  [String](../../dart-core/string-class) name,
2.  {void onBlocked(
    1.  [Event](../../dart-html/event-class) e

    )?}

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<IdbFactory> deleteDatabase(String name, {void onBlocked(Event e)?}) {
  try {
    var request = _deleteDatabase(name);

    if (onBlocked != null) {
      request.onBlocked.listen(onBlocked);
    }
    var completer = new Completer<IdbFactory>.sync();
    request.onSuccess.listen((e) {
      completer.complete(this);
    });
    request.onError.listen(completer.completeError);
    return completer.future;
  } catch (e, stacktrace) {
    return new Future.error(e, stacktrace);
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-indexed_db/IdbFactory/deleteDatabase.html>
:::
