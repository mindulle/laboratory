[dart:html](../../dart-html/dart-html-library){._links-link}

iceCandidateEvent constant
==========================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[RtcPeerConnectionIceEvent](../rtcpeerconnectioniceevent-class)\>
const iceCandidateEvent
:::

Static factory designed to expose `icecandidate` events to event
handlers that are not necessarily instances of
[RtcPeerConnection](../rtcpeerconnection-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<RtcPeerConnectionIceEvent>
    iceCandidateEvent =
    const EventStreamProvider<RtcPeerConnectionIceEvent>('icecandidate');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/RtcPeerConnection/iceCandidateEvent-constant.html>
:::
