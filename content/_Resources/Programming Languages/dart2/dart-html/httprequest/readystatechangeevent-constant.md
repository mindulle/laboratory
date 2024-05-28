[dart:html](../../dart-html/dart-html-library){._links-link}

readyStateChangeEvent constant
==============================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[Event](../event-class)\>
const readyStateChangeEvent
:::

Static factory designed to expose `readystatechange` events to event
handlers that are not necessarily instances of
[HttpRequest](../httprequest-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<Event> readyStateChangeEvent =
    const EventStreamProvider<Event>('readystatechange');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/HttpRequest/readyStateChangeEvent-constant.html>
:::
