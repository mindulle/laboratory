[dart:html](../../dart-html/dart-html-library){._links-link}

getLegacyStats method
=====================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[RtcStatsResponse](../rtcstatsresponse-class)\>
getLegacyStats(

1.  \[[MediaStreamTrack](../mediastreamtrack-class)? selector\]

)
:::

Temporarily exposes \_getStats and old getStats as getLegacyStats until
Chrome fully supports new getStats API.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<RtcStatsResponse> getLegacyStats([MediaStreamTrack? selector]) {
  var completer = new Completer<RtcStatsResponse>();
  _getStats((value) {
    completer.complete(value);
  }, selector);
  return completer.future;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/RtcPeerConnection/getLegacyStats.html>
:::
