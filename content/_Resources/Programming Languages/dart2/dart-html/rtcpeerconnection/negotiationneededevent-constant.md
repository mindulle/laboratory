[dart:html](../../dart-html/dart-html-library){._links-link}

negotiationNeededEvent constant
===============================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[Event](../event-class)\>
const negotiationNeededEvent
:::

Static factory designed to expose `negotiationneeded` events to event
handlers that are not necessarily instances of
[RtcPeerConnection](../rtcpeerconnection-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<Event> negotiationNeededEvent =
    const EventStreamProvider<Event>('negotiationneeded');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/RtcPeerConnection/negotiationNeededEvent-constant.html>
:::
