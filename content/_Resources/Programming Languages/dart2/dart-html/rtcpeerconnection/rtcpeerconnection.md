[dart:html](../../dart-html/dart-html-library){._links-link}

RtcPeerConnection constructor
=============================

::: {.section .multi-line-signature}
RtcPeerConnection(

1.  [Map](../../dart-core/map-class) rtcIceServers,
2.  \[[Map](../../dart-core/map-class)? mediaConstraints\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory RtcPeerConnection(Map rtcIceServers, [Map? mediaConstraints]) {
  var constructorName =
      JS('RtcPeerConnection', 'window[#]', 'RTCPeerConnection');
  if (mediaConstraints != null) {
    return JS(
        'RtcPeerConnection',
        'new #(#,#)',
        constructorName,
        convertDartToNative_SerializedScriptValue(rtcIceServers),
        convertDartToNative_SerializedScriptValue(mediaConstraints));
  } else {
    return JS('RtcPeerConnection', 'new #(#)', constructorName,
        convertDartToNative_SerializedScriptValue(rtcIceServers));
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/RtcPeerConnection/RtcPeerConnection.html>
:::
