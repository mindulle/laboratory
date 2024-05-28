[dart:html](../../dart-html/dart-html-library){._links-link}

onRemoveStream property
=======================

::: {#getter .section .multi-line-signature}
[Stream](../../dart-async/stream-class)\<[MediaStreamEvent](../mediastreamevent-class)\>
onRemoveStream
:::

Stream of `removestream` events handled by this
[RtcPeerConnection](../rtcpeerconnection-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<MediaStreamEvent> get onRemoveStream =>
    removeStreamEvent.forTarget(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/RtcPeerConnection/onRemoveStream.html>
:::
