[dart:html](../../dart-html/dart-html-library){._links-link}

searchEvent constant
====================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[Event](../event-class)\>
const searchEvent
:::

Static factory designed to expose `search` events to event handlers that
are not necessarily instances of [Element](../element-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<Event> searchEvent =
    const EventStreamProvider<Event>('search');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/searchEvent-constant.html>
:::
