[dart:html](../../dart-html/dart-html-library){._links-link}

dataChannelEvent constant
=========================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[RtcDataChannelEvent](../rtcdatachannelevent-class)\>
const dataChannelEvent
:::

Static factory designed to expose `datachannel` events to event handlers
that are not necessarily instances of
[RtcPeerConnection](../rtcpeerconnection-class).

See [EventStreamProvider](../eventstreamprovider-class) for usage
information.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<RtcDataChannelEvent> dataChannelEvent =
    const EventStreamProvider<RtcDataChannelEvent>('datachannel');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/RtcPeerConnection/dataChannelEvent-constant.html>
:::
