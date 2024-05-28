[dart:html](../../dart-html/dart-html-library){._links-link}

checkingEvent constant
======================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[Event](../event-class)\>
const checkingEvent
:::

Static factory designed to expose `checking` events to event handlers
that are not necessarily instances of
[ApplicationCache](../applicationcache-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<Event> checkingEvent =
    const EventStreamProvider<Event>('checking');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/ApplicationCache/checkingEvent-constant.html>
:::
