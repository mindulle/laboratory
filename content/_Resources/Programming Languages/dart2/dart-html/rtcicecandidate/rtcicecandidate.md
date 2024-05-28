[dart:html](../../dart-html/dart-html-library){._links-link}

RtcIceCandidate constructor
===========================

::: {.section .multi-line-signature}
RtcIceCandidate(

1.  [Map](../../dart-core/map-class) dictionary

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory RtcIceCandidate(Map dictionary) {
  var constructorName = JS('', 'window[#]', 'RTCIceCandidate');
  return JS('RtcIceCandidate', 'new #(#)', constructorName,
      convertDartToNative_SerializedScriptValue(dictionary));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/RtcIceCandidate/RtcIceCandidate.html>
:::
