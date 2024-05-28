[dart:html](../../dart-html/dart-html-library){._links-link}

showEvent constant
==================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[Event](../event-class)\>
const showEvent
:::

Static factory designed to expose `show` events to event handlers that
are not necessarily instances of [Notification](../notification-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<Event> showEvent =
    const EventStreamProvider<Event>('show');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Notification/showEvent-constant.html>
:::
