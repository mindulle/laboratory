[dart:html](../../dart-html/dart-html-library){._links-link}

messageEvent constant
=====================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[MessageEvent](../messageevent-class)\>
const messageEvent
:::

Static factory designed to expose `message` events to event handlers
that are not necessarily instances of
[EventSource](../eventsource-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<MessageEvent> messageEvent =
    const EventStreamProvider<MessageEvent>('message');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/EventSource/messageEvent-constant.html>
:::
