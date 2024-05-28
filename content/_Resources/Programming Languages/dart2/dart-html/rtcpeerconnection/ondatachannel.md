[dart:html](../../dart-html/dart-html-library){._links-link}

onDataChannel property
======================

::: {#getter .section .multi-line-signature}
[Stream](../../dart-async/stream-class)\<[RtcDataChannelEvent](../rtcdatachannelevent-class)\>
onDataChannel
:::

Stream of `datachannel` events handled by this
[RtcPeerConnection](../rtcpeerconnection-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<RtcDataChannelEvent> get onDataChannel =>
    dataChannelEvent.forTarget(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/RtcPeerConnection/onDataChannel.html>
:::
