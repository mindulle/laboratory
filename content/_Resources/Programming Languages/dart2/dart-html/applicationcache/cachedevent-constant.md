[dart:html](../../dart-html/dart-html-library){._links-link}

cachedEvent constant
====================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[Event](../event-class)\>
const cachedEvent
:::

Static factory designed to expose `cached` events to event handlers that
are not necessarily instances of
[ApplicationCache](../applicationcache-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<Event> cachedEvent =
    const EventStreamProvider<Event>('cached');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/ApplicationCache/cachedEvent-constant.html>
:::
