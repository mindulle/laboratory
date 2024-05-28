[dart:html](../../dart-html/dart-html-library){._links-link}

removeStreamEvent constant
==========================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[MediaStreamEvent](../mediastreamevent-class)\>
const removeStreamEvent
:::

Static factory designed to expose `removestream` events to event
handlers that are not necessarily instances of
[RtcPeerConnection](../rtcpeerconnection-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<MediaStreamEvent> removeStreamEvent =
    const EventStreamProvider<MediaStreamEvent>('removestream');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/RtcPeerConnection/removeStreamEvent-constant.html>
:::
