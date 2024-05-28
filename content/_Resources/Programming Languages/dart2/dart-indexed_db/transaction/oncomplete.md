[dart:indexed\_db](../../dart-indexed_db/dart-indexed_db-library){._links-link}

onComplete property
===================

::: {#getter .section .multi-line-signature}
[Stream](../../dart-async/stream-class)\<[Event](../../dart-html/event-class)\>
onComplete
:::

Stream of `complete` events handled by this
[Transaction](../transaction-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<Event> get onComplete => completeEvent.forTarget(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-indexed_db/Transaction/onComplete.html>
:::
