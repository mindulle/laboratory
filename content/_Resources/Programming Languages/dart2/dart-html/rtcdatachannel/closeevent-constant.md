[dart:html](../../dart-html/dart-html-library){._links-link}

closeEvent constant
===================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[Event](../event-class)\>
const closeEvent
:::

Static factory designed to expose `close` events to event handlers that
are not necessarily instances of
[RtcDataChannel](../rtcdatachannel-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<Event> closeEvent =
    const EventStreamProvider<Event>('close');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/RtcDataChannel/closeEvent-constant.html>
:::
