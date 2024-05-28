[dart:html](../../dart-html/dart-html-library){._links-link}

storageEvent constant
=====================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[StorageEvent](../storageevent-class)\>
const storageEvent
:::

Static factory designed to expose `storage` events to event handlers
that are not necessarily instances of [Window](../window-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<StorageEvent> storageEvent =
    const EventStreamProvider<StorageEvent>('storage');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Window/storageEvent-constant.html>
:::
