[dart:html](../../dart-html/dart-html-library){._links-link}

onTrack property
================

::: {#getter .section .multi-line-signature}
[Stream](../../dart-async/stream-class)\<[RtcTrackEvent](../rtctrackevent-class)\>
onTrack
:::

Stream of `track` events handled by this
[RtcPeerConnection](../rtcpeerconnection-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<RtcTrackEvent> get onTrack => trackEvent.forTarget(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/RtcPeerConnection/onTrack.html>
:::
