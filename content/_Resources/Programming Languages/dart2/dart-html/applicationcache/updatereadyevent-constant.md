[dart:html](../../dart-html/dart-html-library){._links-link}

updateReadyEvent constant
=========================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[Event](../event-class)\>
const updateReadyEvent
:::

Static factory designed to expose `updateready` events to event handlers
that are not necessarily instances of
[ApplicationCache](../applicationcache-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<Event> updateReadyEvent =
    const EventStreamProvider<Event>('updateready');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/ApplicationCache/updateReadyEvent-constant.html>
:::
