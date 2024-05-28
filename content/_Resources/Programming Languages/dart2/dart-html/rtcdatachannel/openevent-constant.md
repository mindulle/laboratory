[dart:html](../../dart-html/dart-html-library){._links-link}

openEvent constant
==================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[Event](../event-class)\>
const openEvent
:::

Static factory designed to expose `open` events to event handlers that
are not necessarily instances of
[RtcDataChannel](../rtcdatachannel-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<Event> openEvent =
    const EventStreamProvider<Event>('open');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/RtcDataChannel/openEvent-constant.html>
:::
