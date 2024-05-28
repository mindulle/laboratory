[dart:indexed\_db](../../dart-indexed_db/dart-indexed_db-library){._links-link}

closeEvent constant
===================

::: {.section .multi-line-signature}
[EventStreamProvider](../../dart-html/eventstreamprovider-class)\<[Event](../../dart-html/event-class)\>
const closeEvent
:::

Static factory designed to expose `close` events to event handlers that
are not necessarily instances of [Database](../database-class).

See [EventStreamProvider](../../dart-html/eventstreamprovider-class) for
usage information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<Event> closeEvent =
    const EventStreamProvider<Event>('close');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-indexed_db/Database/closeEvent-constant.html>
:::
