[dart:html](../../dart-html/dart-html-library){._links-link}

offlineEvent constant
=====================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[Event](../event-class)\>
const offlineEvent
:::

Static factory designed to expose `offline` events to event handlers
that are not necessarily instances of [Window](../window-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<Event> offlineEvent =
    const EventStreamProvider<Event>('offline');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Window/offlineEvent-constant.html>
:::
