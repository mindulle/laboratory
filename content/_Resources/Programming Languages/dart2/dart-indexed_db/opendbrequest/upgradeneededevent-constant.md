[dart:indexed\_db](../../dart-indexed_db/dart-indexed_db-library){._links-link}

upgradeNeededEvent constant
===========================

::: {.section .multi-line-signature}
[EventStreamProvider](../../dart-html/eventstreamprovider-class)\<[VersionChangeEvent](../versionchangeevent-class)\>
const upgradeNeededEvent
:::

Static factory designed to expose `upgradeneeded` events to event
handlers that are not necessarily instances of
[OpenDBRequest](../opendbrequest-class).

See [EventStreamProvider](../../dart-html/eventstreamprovider-class) for
usage information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<VersionChangeEvent> upgradeNeededEvent =
    const EventStreamProvider<VersionChangeEvent>('upgradeneeded');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-indexed_db/OpenDBRequest/upgradeNeededEvent-constant.html>
:::
