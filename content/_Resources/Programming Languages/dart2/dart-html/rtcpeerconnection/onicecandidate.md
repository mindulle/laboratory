[dart:html](../../dart-html/dart-html-library){._links-link}

onIceCandidate property
=======================

::: {#getter .section .multi-line-signature}
[Stream](../../dart-async/stream-class)\<[RtcPeerConnectionIceEvent](../rtcpeerconnectioniceevent-class)\>
onIceCandidate
:::

Stream of `icecandidate` events handled by this
[RtcPeerConnection](../rtcpeerconnection-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<RtcPeerConnectionIceEvent> get onIceCandidate =>
    iceCandidateEvent.forTarget(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/RtcPeerConnection/onIceCandidate.html>
:::
